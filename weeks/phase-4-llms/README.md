# Phase 4: LLMs & Generative AI (Weeks 17–20)

## Overview

This is where the 2026 hiring bar lives. Every top AI company is building with LLMs — and they need engineers who understand the full stack from prompting to fine-tuning to deployment.

**Key principle**: Go beyond API calls. Understand what's happening under the hood.

---

## Week 17: LLM Architecture, Tokenization & Prompting

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Course | [HuggingFace LLM Course](https://huggingface.co/learn/llm-course/chapter1/1) — Ch 1–3 | 6 hrs |
| 📖 Guide | [OpenAI Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering) | 1 hr |
| 📖 Guide | [Anthropic Prompt Engineering Docs](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering) | 1 hr |
| 📺 Video | Karpathy: "Let's build the GPT tokenizer" | 2 hrs |

### What to Build
- Tokenizer comparison: BPE vs SentencePiece vs tiktoken (visualize how same text tokenizes differently)
- Decoding strategy comparison: greedy vs beam vs top-k vs top-p vs temperature (show output quality tradeoffs)
- **Prompt evaluation framework**:
  - Test 10+ prompt variants on same task
  - Measure accuracy, consistency, latency
  - Track results in structured format

### Interview Connection
- "How does BPE tokenization work?" (OpenAI, Anthropic)
- "Explain temperature and top-p" (everywhere)
- "How would you systematically improve prompt quality?" (Amazon Bedrock, any LLM team)

---

## Week 18: RAG (Retrieval Augmented Generation)

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Course | [DeepLearning.AI: Building and Evaluating Advanced RAG](https://www.deeplearning.ai/short-courses/) | 2 hrs |
| 📖 Docs | LlamaIndex documentation | Reference |
| 📖 Docs | LangChain RAG tutorial | Reference |
| 📖 Blog | Pinecone: "RAG Architecture" guide | 1 hr |

### What to Build
- **Production-quality RAG system**:
  1. Data ingestion pipeline (PDF/web → chunks)
  2. Chunking comparison: fixed (512 tokens) vs recursive vs semantic
  3. Embedding model comparison: OpenAI vs sentence-transformers vs Cohere
  4. Vector store: FAISS (local) or Chroma
  5. Hybrid search: semantic + BM25 keyword
  6. Reranker: cross-encoder reranking
  7. Evaluation: precision@k, recall@k, answer relevance, faithfulness
- Deploy as web app (Streamlit/Gradio)

### Interview Connection
- "Design a RAG system for [domain]" — THE #1 asked LLM system design question in 2026
- "How do you evaluate retrieval quality?" (Amazon, Google)
- "What are failure modes of RAG?" (hallucination from irrelevant context, stale data, chunk boundary issues)

---

## Week 19: Fine-Tuning LLMs

### Resources
| Type | Resource | Time |
|---|---|---|
| 📖 Docs | [HuggingFace PEFT Library](https://huggingface.co/docs/peft) | 2 hrs |
| 📖 Blog | Sebastian Raschka: "LoRA & QLoRA Explained" | 1 hr |
| 📖 Docs | [HuggingFace TRL (RLHF)](https://huggingface.co/docs/trl) | 2 hrs |
| 📺 Course | HuggingFace LLM Course Ch 4–6 | 4 hrs |

### Topics to Master
| Topic | What to Know |
|---|---|
| Full fine-tuning | When to use, VRAM requirements, catastrophic forgetting |
| LoRA | Low-rank adaptation, rank selection, which layers to adapt |
| QLoRA | 4-bit quantized base + LoRA adapters, NF4 data type |
| Instruction tuning | Chat templates, system prompts, dataset formatting |
| DPO/RLHF | Preference learning, reward models, PPO vs DPO tradeoffs |
| Quantization | GPTQ, AWQ, GGUF — speed vs quality tradeoff |
| Inference | vLLM, KV-cache, continuous batching, speculative decoding |

### What to Build
- Fine-tune Llama 3/Mistral 7B with QLoRA on custom instruction dataset
- Compare: base model vs fine-tuned (quality + latency benchmarks)
- Quantize to 4-bit: benchmark quality degradation
- Serve with vLLM: measure tokens/sec, latency p50/p95
- Publish model card on HuggingFace

### Interview Connection
- "How does LoRA work and why is it effective?" (Amazon, OpenAI, Anthropic)
- "Explain RLHF pipeline" — Anthropic's core business (alignment)
- "How would you reduce inference cost by 10x?" — inference optimization (OpenAI, Google)

---

## Week 20: AI Agents + LLM Capstone ⭐

### Resources
| Type | Resource | Time |
|---|---|---|
| 📖 Docs | [OpenAI Agents SDK](https://openai.github.io/openai-agents-python/) | 2 hrs |
| 📖 Docs | [LangGraph](https://langchain-ai.github.io/langgraph/) | 2 hrs |
| 📺 Course | Andrew Ng: Agentic AI (DeepLearning.AI) | 2 hrs |

### Topics to Master
- Agent architectures: ReAct, tool-use, planning (plan-and-execute)
- Multi-agent orchestration: supervisor, swarm, hierarchical
- Memory systems: conversation, episodic, semantic
- Tool integration: function calling, code execution, web search
- Guardrails: output validation, safety filters, content moderation
- Evaluation: task completion rate, tool selection accuracy, safety violations

### Capstone Project
**Build and deploy a multi-tool AI agent:**
- Example: Research Agent that can search the web, read papers, summarize, and answer questions
- Include: tool use, memory (conversation history), error handling
- Evaluation harness: 20+ test cases with expected behavior
- Deploy: Streamlit frontend + FastAPI backend
- Push to HuggingFace Spaces for public demo

### Deliverables
- [ ] Working agent deployed publicly
- [ ] Evaluation results documented
- [ ] Architecture diagram
- [ ] Demo video for LinkedIn
- [ ] Blog: "Building Production AI Agents: What Works and What Doesn't"

### Interview Connection
- Agent architecture is THE hottest topic in 2026 interviews
- Amazon Copilot, Meta AI, Google Gemini, Anthropic Claude — all agent-based
- "Design an AI agent for [task]" — new system design question format

---

## 🎯 Phase 4 Completion Criteria

You're ready for Phase 5 when you can:
- [ ] Explain BPE tokenization and why it matters for model performance
- [ ] Build a RAG system and evaluate it (not just "it works" — quantitative metrics)
- [ ] Fine-tune an LLM with LoRA and explain the math (low-rank decomposition)
- [ ] Explain the RLHF pipeline (reward model → PPO or DPO)
- [ ] Build an AI agent with tool use and proper error handling
- [ ] Have a deployed LLM application accessible via URL
- [ ] Published model card on HuggingFace
