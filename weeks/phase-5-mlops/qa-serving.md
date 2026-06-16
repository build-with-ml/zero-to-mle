# ❓ Q&A: Model Serving (Week 21)

Questions and answers collected during study.

---

### Q: Batch inference vs real-time serving — when to use which?

**Context**: Designing a model serving architecture for an ML system design interview.

**Answer**: 

| | Batch Inference | Real-Time Serving |
|---|---|---|
| **Latency** | Minutes to hours | Milliseconds to seconds |
| **When** | Scheduled (daily/hourly) | On request |
| **Use case** | Recommendation pre-computation, reporting, bulk scoring | Search ranking, fraud detection, chatbots |
| **Infra** | Spark/Airflow + model | API server + model (FastAPI, Ray Serve) |
| **Cost** | Cheaper (spot instances, no SLA) | More expensive (always-on, latency SLA) |
| **Freshness** | Stale (hours-old predictions) | Fresh (uses latest features) |

Hybrid pattern (common in production):
- **Batch**: Pre-compute top-100 recommendations for all users (offline)
- **Real-time**: Re-rank those 100 based on current session context (online)

When real-time is mandatory:
- Fraud detection (can't wait hours to block a transaction)
- Search/ads (personalized to current query)
- Chat/conversational AI (interactive)

**Key Insight**: Most production systems use BOTH — batch for expensive pre-computation, real-time for final personalization. This is the two-stage retrieval+ranking pattern.

**Tags**: `#serving` `#batch` `#real-time` `#system-design` `#interview-relevant`

---

<!-- ADD MORE Q&A BELOW -->
