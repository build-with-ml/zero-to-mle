# Transformers — Q&A

Questions and answers collected while studying Phase 3, Weeks 14–15.

---

### Q: Why is self-attention O(n²) and why does that matter?

**Context**: Building mini-GPT, wondering about context length limitations.

**Answer**: 
In self-attention, every token attends to every other token. For a sequence of length n:
- Attention matrix = Q × Kᵀ = (n × d) × (d × n) = n × n matrix
- Memory: O(n²) to store the attention weights
- Compute: O(n² × d) for the matrix multiplications

This means:
- Doubling context length → 4× the memory and compute
- GPT-4's 128K context window requires enormous memory
- This is why efficient attention variants exist (Flash Attention, sparse attention, linear attention)

Solutions in practice:
1. **Flash Attention**: Same result, but IO-aware — reduces memory reads/writes
2. **Sliding window attention** (Mistral): Only attend to local context
3. **KV-cache**: During inference, don't recompute past keys/values
4. **Ring Attention**: Distribute across GPUs for very long contexts

**Key Insight**: The quadratic cost is why context length was the main bottleneck for LLMs. Flash Attention didn't change the math — it changed the memory access pattern to be GPU-friendly.

**Tags**: `#transformers` `#attention` `#complexity` `#interview-relevant`

---

### Q: What is KV-cache and why does it speed up inference?

**Context**: Learning about LLM serving optimization for the MLOps phase.

**Answer**: 
During autoregressive generation (producing one token at a time):
- Without KV-cache: For each new token, recompute attention over ALL previous tokens from scratch
- With KV-cache: Store the Key and Value matrices from previous tokens, only compute Q for the new token

Example (generating token 100):
- Without cache: Compute attention for all 100 tokens → O(100² × d)
- With cache: Look up cached K,V for tokens 1–99, compute Q for token 100 → O(100 × d)

The catch: KV-cache uses a lot of memory (grows linearly with sequence length × batch size × layers × heads). This is often the memory bottleneck in LLM serving, not the model weights.

Optimizations:
- **Multi-Query Attention (MQA)**: Share K,V heads across queries → smaller cache
- **Grouped-Query Attention (GQA)**: Compromise between MHA and MQA
- **PagedAttention (vLLM)**: Manage KV-cache like virtual memory pages

**Key Insight**: KV-cache turns inference from O(n²) per token to O(n) per token, but the memory cost is why serving LLMs is expensive. This is THE bottleneck in production LLM systems.

**Tags**: `#transformers` `#inference` `#optimization` `#mlops` `#interview-relevant`

---

### Q: What's the difference between encoder-only, decoder-only, and encoder-decoder Transformers?

**Context**: Confused about why BERT vs GPT vs T5 have different architectures.

**Answer**: 

| Architecture | Attention Type | Training | Use Case | Examples |
|---|---|---|---|---|
| **Encoder-only** | Bidirectional (sees all tokens) | Masked Language Modeling | Classification, embeddings, NER | BERT, RoBERTa |
| **Decoder-only** | Causal/masked (sees only past) | Next token prediction | Text generation, chat, code | GPT, Llama, Mistral |
| **Encoder-Decoder** | Encoder=bidir, Decoder=causal + cross-attention | Seq2seq (e.g., translation) | Translation, summarization | T5, BART |

Why decoder-only won:
1. **Simpler** — one architecture, one training objective
2. **Scales better** — emergent abilities appear with scale
3. **Generalist** — generation subsumes classification (you can classify by generating the label)
4. **In-context learning** — few-shot prompting works naturally with autoregressive models

**Key Insight**: The industry converged on decoder-only (GPT-style) because generation is the most general capability — a model that can generate well can also classify, summarize, translate, and reason.

**Tags**: `#transformers` `#architecture` `#llm` `#interview-relevant`

---

<!-- Add more Q&A entries below as you learn -->
