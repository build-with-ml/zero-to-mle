# Phase 5: MLOps & Production ML (Weeks 21–23)

## Overview

This is what separates an MLE from a Data Scientist. You don't just train models — you **deploy, monitor, and maintain them in production**. This is heavily tested at Amazon and Google.

**Key principle**: Follow [Made With ML](https://madewithml.com) as your primary guide. Supplement with MLOps Zoomcamp.

---

## Week 21: Model Serving & Containerization

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Course | Made With ML — Serving, Testing sections | 4 hrs |
| 📺 Course | [MLOps Zoomcamp Module 4](https://github.com/DataTalksClub/mlops-zoomcamp) | 3 hrs |
| 📖 Docs | FastAPI documentation | Reference |
| 📖 Docs | Docker official guide | Reference |

### What to Build
- **Production ML API**:
  1. FastAPI app with `/predict`, `/health`, `/metrics` endpoints
  2. Request/response schema validation (Pydantic)
  3. Input preprocessing + model inference + post-processing
  4. Batch prediction endpoint
  5. Async request handling
  6. Error handling with proper HTTP status codes
- **Containerization**:
  1. Multi-stage Dockerfile (small image)
  2. Docker Compose with model server + database
  3. Environment variable configuration
- **Benchmarking**:
  - Measure latency p50/p95/p99
  - Measure throughput (requests/second)
  - Load testing with locust

### Serving Framework Comparison (know the tradeoffs)
| Framework | Best For | Latency | Scalability |
|---|---|---|---|
| FastAPI | Simple models, prototyping | Low | Manual |
| Ray Serve | Multi-model, auto-scaling | Low | Auto |
| vLLM | LLM inference | Optimized | Auto |
| Triton | Multi-framework, GPU inference | Very low | Enterprise |
| TorchServe | PyTorch models | Medium | Manual |

### Interview Connection
- "How would you deploy this model?" — every Amazon ML system design round
- "What's your serving architecture for 10K QPS?" — Meta, Google
- "How do you handle model versioning in production?" — MLOps judgment

---

## Week 22: ML Pipelines, Experiment Tracking & CI/CD

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Course | Made With ML — Orchestration, CI/CD sections | 4 hrs |
| 📺 Course | MLOps Zoomcamp Modules 2–3, 5–6 | 6 hrs |
| 📖 Docs | [MLflow documentation](https://mlflow.org/docs/latest/index.html) | Reference |
| 📖 Docs | [Prefect documentation](https://docs.prefect.io/) | Reference |

### What to Build
- **Experiment Tracking (MLflow)**:
  - Log all previous projects to MLflow
  - Track: params, metrics, artifacts, model versions
  - Model registry: staging → production promotion
  - Compare experiments in MLflow UI
- **Training Pipeline (Prefect or similar)**:
  1. Data fetch + validation
  2. Feature engineering
  3. Model training
  4. Evaluation (with quality gates)
  5. Model registration (if metrics pass)
  6. Notification on failure
- **CI/CD for ML (GitHub Actions)**:
  - On push: lint → test → type-check
  - On PR: train on small dataset → evaluate → report metrics
  - On merge to main: full training → deploy (if metrics pass)
  - Model quality gates (don't deploy if accuracy drops)

### Key Concepts
| Concept | What to Know |
|---|---|
| Feature Store | Centralized feature computation + serving (Feast) |
| Model Registry | Version models, promote staging → prod (MLflow) |
| Data Versioning | Track dataset versions (DVC) |
| Pipeline Orchestration | DAG-based workflow execution (Prefect, Airflow) |
| Shadow Deployment | Run new model alongside old, compare |
| Canary Deployment | Route small % of traffic to new model |
| A/B Testing | Statistical comparison of model versions |

### Interview Connection
- "How do you retrain models?" — Amazon, Google system design
- "How do you ensure model quality before deployment?" — CI/CD gates
- "Walk me through your ML pipeline" — common opening in ML system design

---

## Week 23: Monitoring, Drift Detection & CAPSTONE ⭐⭐⭐

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Course | Made With ML — Monitoring section | 2 hrs |
| 📺 Course | MLOps Zoomcamp Module 7 | 3 hrs |
| 📖 Docs | [Evidently AI](https://docs.evidentlyai.com/) | Reference |
| 📖 Book | "Designing ML Systems" (Chip Huyen) Ch. 8–9 | 2 hrs |

### Topics to Master
| Type of Drift | Description | Detection |
|---|---|---|
| Data drift | Input distribution changes | PSI, KS test, Evidently |
| Concept drift | Relationship between X and Y changes | Performance monitoring |
| Prediction drift | Model output distribution changes | Statistical tests |
| Feature drift | Individual feature distributions shift | Per-feature monitoring |

### What to Build
- **Monitoring dashboard** with Evidently:
  - Data quality checks (missing values, schema violations)
  - Feature drift detection (PSI, KS test)
  - Prediction drift alerts
  - Performance monitoring (if labels available)
- **Automated alerting**: trigger retraining when drift exceeds threshold
- **Simulate drift**: artificially shift data distribution, show detection working

### CAPSTONE PROJECT: Full Production ML System ⭐

**This is your portfolio crown jewel.** Build a complete system:

```
Data Source → Ingestion → Validation → Feature Engineering
     → Training (with experiment tracking)
     → Evaluation (with quality gates)
     → Model Registry
     → Serving (containerized API)
     → Monitoring (drift detection + alerting)
     → Automated Retraining (triggered by drift)
```

**Requirements:**
- [ ] Automated training pipeline (Prefect/Airflow)
- [ ] Experiment tracking (MLflow)
- [ ] Containerized model serving (Docker + FastAPI)
- [ ] CI/CD pipeline (GitHub Actions)
- [ ] Drift monitoring (Evidently)
- [ ] Integration tests
- [ ] Load testing results
- [ ] Architecture diagram
- [ ] Comprehensive README

**Deliverables:**
- GitHub repo (this becomes your flagship project)
- Blog series: "Production ML from Scratch" (3 parts: serving, pipelines, monitoring)
- Architecture diagram on LinkedIn
- Live demo (if possible)

### Interview Connection
- This project directly maps to what Amazon/Meta/Google test in ML system design rounds
- "Design an ML system for X" — you can draw from this real experience
- Shows production judgment — the #1 differentiator for MLE vs Data Scientist

---

## 🎯 Phase 5 Completion Criteria

You're ready for Phase 6 when you can:
- [ ] Deploy a model behind a production-grade API with proper error handling
- [ ] Explain your CI/CD pipeline for ML (what triggers what, quality gates)
- [ ] Detect data drift and explain what actions to take
- [ ] Draw an end-to-end ML system architecture diagram from memory
- [ ] Explain tradeoffs: batch vs online serving, shadow vs A/B deployment
- [ ] Your capstone project is deployed and documented
- [ ] Published "Production ML" blog series
