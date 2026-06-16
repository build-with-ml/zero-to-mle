# ❓ Q&A: RAG — Retrieval Augmented Generation (Week 18)

Questions and answers collected during study.

---

### Q: What are the main failure modes of RAG systems?

**Context**: Building a RAG system, trying to anticipate what can go wrong.

**Answer**: 
1. **Bad retrieval → wrong context**: Retrieved chunks don't contain the answer
   - Fix: Better chunking, hybrid search, reranking, evaluation of retrieval
2. **Hallucination despite good context**: Model ignores retrieved context
   - Fix: Stronger prompting ("Only answer from provided context"), smaller models hallucinate more
3. **Chunk boundary problems**: Answer spans two chunks but only one is retrieved
   - Fix: Overlapping chunks, larger chunk size, recursive retrieval
4. **Stale data**: Retrieved information is outdated
   - Fix: Metadata timestamps, re-index regularly, show source dates to user
5. **Lost in the middle**: With many retrieved chunks, model ignores middle ones
   - Fix: Limit to top 3–5 chunks, rerank before insertion, put most relevant first/last
6. **Embedding model mismatch**: Query and document encoded differently
   - Fix: Use same embedding model for indexing and querying, fine-tune embeddings on your domain

**Key Insight**: RAG systems fail silently — they generate confident-sounding wrong answers. You MUST evaluate retrieval quality separately from generation quality.

**Tags**: `#rag` `#failure-modes` `#evaluation` `#interview-relevant`

---

<!-- ADD MORE Q&A BELOW -->
