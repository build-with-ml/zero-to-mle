# Project 4: Full Production ML System (Capstone) ⭐

## Overview
The flagship portfolio project. A complete ML system with training pipeline, model serving, CI/CD, and monitoring.

## When to Build
Week 23 (end of Phase 5)

## Architecture

```
┌─────────────┐     ┌──────────────┐     ┌─────────────┐
│ Data Source  │────▶│  Ingestion   │────▶│ Validation  │
└─────────────┘     └──────────────┘     └──────┬──────┘
                                                  │
                    ┌──────────────┐     ┌────────▼──────┐
                    │   MLflow     │◀────│   Training    │
                    │  (tracking)  │     │   Pipeline    │
                    └──────┬───────┘     └───────────────┘
                           │
                    ┌──────▼───────┐     ┌───────────────┐
                    │    Model     │────▶│   Serving     │
                    │  Registry    │     │  (FastAPI)    │
                    └──────────────┘     └───────┬───────┘
                                                  │
                    ┌──────────────┐     ┌────────▼──────┐
                    │  Alerting &  │◀────│  Monitoring   │
                    │  Retraining  │     │  (Evidently)  │
                    └──────────────┘     └───────────────┘
```

## Requirements
- [ ] Automated training pipeline (Prefect or Airflow)
- [ ] Experiment tracking (MLflow)
- [ ] Model registry with versioning
- [ ] Containerized model serving (Docker + FastAPI)
- [ ] CI/CD pipeline (GitHub Actions)
- [ ] Data validation (Great Expectations or custom)
- [ ] Drift monitoring (Evidently)
- [ ] Integration tests
- [ ] Load testing (locust)
- [ ] Architecture documentation
- [ ] Comprehensive README with setup instructions

## Components

### 1. Data Pipeline
- Scheduled data ingestion
- Data quality checks (schema, ranges, nulls)
- Feature engineering (reproducible)
- Train/test split versioning

### 2. Training Pipeline
- Triggered by: schedule, drift alert, or manual
- Hyperparameter optimization
- Experiment logging to MLflow
- Model evaluation with quality gates
- Auto-registration if metrics pass

### 3. Serving
- FastAPI with /predict, /health, /metrics endpoints
- Docker containerized
- Batch + real-time prediction
- Model versioning (canary deployments)

### 4. CI/CD
- On push: lint, test, type-check
- On PR: train on subset, report metrics
- On merge: full pipeline execution
- Deployment gates: only deploy if metrics improve

### 5. Monitoring
- Data drift detection (PSI, KS test)
- Prediction drift tracking
- Performance monitoring (if labels available)
- Alerting thresholds
- Automated retraining trigger

## Deliverables
- [ ] GitHub repository (PORTFOLIO CROWN JEWEL)
- [ ] Blog series: "Production ML from Scratch" (3 parts)
- [ ] Architecture diagram on LinkedIn
- [ ] Live demo (if possible)
- [ ] Load testing results

## Structure
```
project-4-mlops/
├── README.md
├── src/
│   ├── data/
│   │   ├── ingest.py
│   │   └── validate.py
│   ├── features/
│   │   └── engineer.py
│   ├── training/
│   │   ├── train.py
│   │   └── evaluate.py
│   ├── serving/
│   │   ├── app.py
│   │   ├── schemas.py
│   │   └── predict.py
│   └── monitoring/
│       ├── drift.py
│       └── alerts.py
├── pipelines/
│   └── training_pipeline.py
├── tests/
│   ├── test_data.py
│   ├── test_model.py
│   └── test_api.py
├── .github/
│   └── workflows/
│       ├── ci.yml
│       └── deploy.yml
├── docker/
│   ├── Dockerfile
│   └── docker-compose.yml
├── configs/
│   ├── training.yaml
│   └── serving.yaml
├── docs/
│   └── architecture.md
└── requirements.txt
```
