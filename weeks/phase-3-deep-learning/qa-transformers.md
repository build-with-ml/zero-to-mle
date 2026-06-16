# ❓ Q&A: Transformers (Weeks 14–15)

Questions and answers collected during study.

---

### Q: Why is self-attention O(n²) and why does that matter?

**Context**: Building mini-GPT, wondering about context length limitations.

**Answer**: 
In self-attention, every token attends to every other token. For a sequence of length n:
- Attention matrix = Q × Kᵀ = n × n matrix
- Memory: O(n²) to store attention weights
- Compute: O(n² × d) for the matrix multiplications

Doubling context length → 4× the memory and compute.

Solutions in practice:
1. **Flash Attention**: Same math, but IO-aware — reduces memory reads/writes on GPU
2. **Sliding window attention** (Mistral): Only attend to local window
3. **KV-cache**: During inference, don't recompute past keys/values
4. **Ring Attention**: Distribute across GPUs for very long contexts

**Key Insight**: Flash Attention didn't change the math — it changed the memory access pattern to be GPU-friendly. The quadratic cost is why context length was the main bottleneck for LLMs.

**Tags**: `#transformers` `#attention` `#complexity` `#interview-relevant`

---

### Q: What is KV-cache and why does it speed up inference?

**Context**: Learning about LLM serving optimization.

**Answer**: 
During autoregressive generation (one token at a time):
- Without KV-cache: For each new token, recompute attention over ALL previous tokens
- With KV-cache: Store the Key and Value matrices from previous tokens, only compute Q for the new token

Generating token 100:
- Without cache: O(100² × d) — recompute everything
- With cache: O(100 × d) — just attend new Q to cached K,V

The catch: KV-cache uses a lot of memory (grows with sequence length × batch × layers × heads).

Optimizations:
- **Multi-Query Attention (MQA)**: Share K,V heads → smaller cache
- **Grouped-Query Attention (GQA)**: Llama 2/3's approach, compromise between MHA and MQA
- **PagedAttention (vLLM)**: Manage KV-cache like OS virtual memory pages

**Key Insight**: KV-cache turns inference from O(n²) per token to O(n) per token. Memory cost of KV-cache is THE bottleneck in production LLM serving.

**Tags**: `#transformers` `#inference` `#kv-cache` `#mlops` `#interview-relevant`

---

### Q: Why did decoder-only (GPT) win over encoder-decoder (T5) and encoder-only (BERT)?

**Context**: Understanding architecture choices for modern LLMs.

**Answer**: 
| Architecture | Attention | Training | Best For | Examples |
|---|---|---|---|---|
| Encoder-only | Bidirectional | Masked LM | Classification, embeddings | BERT |
| Decoder-only | Causal (past only) | Next token prediction | Generation, chat | GPT, Llama |
| Encoder-Decoder | Mixed | Seq2seq | Translation, summarization | T5, BART |

Why decoder-only won:
1. **Simpler** — one architecture, one loss function
2. **Scales better** — emergent abilities appear with scale
3. **Generalist** — generation subsumes classification (generate the label)
4. **In-context learning** — few-shot works naturally with autoregressive models
5. **Unified API** — everything is text-in, text-out

**Key Insight**: Generation is the most general capability. A model that generates well can also classify, summarize, translate, and reason — making separate architectures unnecessary.

**Tags**: `#transformers` `#architecture` `#llm` `#interview-relevant`

---

<!-- ADD MORE Q&A BELOW -->
