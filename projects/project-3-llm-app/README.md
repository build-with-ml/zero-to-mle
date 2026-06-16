# Project 3: LLM Application (RAG or AI Agent)

## Overview
Build and deploy a production-quality LLM application — either a RAG system or multi-tool AI agent.

## When to Build
Week 20 (end of Phase 4)

## Option A: RAG System
- Document ingestion pipeline
- Chunking strategy comparison
- Vector store + hybrid search
- Reranking pipeline
- Evaluation framework (retrieval + generation quality)
- Web UI (Streamlit/Gradio)

## Option B: AI Agent
- Multi-tool agent with function calling
- Memory system (conversation + episodic)
- Error handling and fallbacks
- Evaluation harness (20+ test cases)
- Web UI with streaming responses

## Requirements
- Deployed publicly (HuggingFace Spaces, Streamlit Cloud, or similar)
- Evaluation metrics documented (not just "it works")
- Architecture diagram
- Demo video for LinkedIn

## Deliverables
- [ ] Working deployed application
- [ ] Evaluation results
- [ ] Architecture diagram
- [ ] Demo video
- [ ] Blog post
- [ ] HuggingFace Space or live URL

## Structure
```
project-3-llm-app/
├── README.md
├── app/
│   ├── main.py          # FastAPI backend
│   ├── agent.py         # Agent / RAG logic
│   ├── tools.py         # Tool definitions
│   └── ui.py            # Streamlit/Gradio frontend
├── evaluation/
│   ├── test_cases.json
│   ├── evaluate.py
│   └── results.md
├── docs/
│   └── architecture.md
├── Dockerfile
├── docker-compose.yml
└── requirements.txt
```
