# ❓ Q&A: Fine-Tuning LLMs (Week 19)

Questions and answers collected during study.

---

### Q: When should I fine-tune vs just use prompting/RAG?

**Context**: Deciding approach for a domain-specific task.

**Answer**: 

| Approach | When to Use | Cost | Data Needed |
|---|---|---|---|
| **Prompting** | Task is well-defined, model already capable | Low (API calls) | 0–20 examples |
| **RAG** | Need factual grounding, data changes often | Medium (embeddings + vector DB) | Documents |
| **Fine-tuning** | Need style/format consistency, domain adaptation, or the model lacks capability | High (GPU, training) | 100–10K examples |
| **Full training** | Building a foundation model | Very high | Millions+ tokens |

Fine-tune when:
- Prompting can't achieve the output format consistently
- You need the model to learn domain-specific patterns (medical, legal, code)
- Latency matters (fine-tuned smaller model > prompted larger model)
- You want to remove capabilities (safety, narrow focus)

DON'T fine-tune when:
- RAG can solve it (adding knowledge is cheaper than baking it in)
- You have <50 high-quality examples
- The task works well with few-shot prompting already

**Key Insight**: Fine-tuning teaches behavior/style/format. RAG teaches facts/knowledge. Use both together for best results (fine-tune for style + RAG for grounding).

**Tags**: `#fine-tuning` `#rag` `#prompting` `#decision-framework` `#interview-relevant`

---

<!-- ADD MORE Q&A BELOW -->
