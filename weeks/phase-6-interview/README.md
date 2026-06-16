# Phase 6: System Design & Interview Prep (Week 24+)

## Overview

You've built the skills. Now prepare to demonstrate them under pressure. ML System Design is the make-or-break round at every top company.

**Key principle**: Practice with a timer. 45 minutes. Out loud. Record yourself.

---

## ML System Design Framework

Use this framework for EVERY design question (memorize it):

### The 8-Step Framework (45 minutes)

| Step | Time | What to Cover |
|---|---|---|
| 1. Clarify Requirements | 3 min | Business goal, scale, latency, users, constraints |
| 2. Define Metrics | 3 min | Offline (AUC, F1), Online (CTR, revenue), Guardrails |
| 3. Data | 5 min | Sources, labeling, volume, freshness, privacy |
| 4. Feature Engineering | 5 min | Feature types, feature store, real-time vs batch |
| 5. Model | 8 min | Architecture choice, training, tradeoffs |
| 6. Evaluation | 5 min | Offline eval, online A/B testing, failure modes |
| 7. Serving | 8 min | Batch vs online, latency, throughput, caching |
| 8. Monitoring & Iteration | 5 min | Drift, retraining, feedback loops, versioning |

---

## Practice Problems (Do All 8)

### 1. Recommendation System
- **Context**: Amazon product recommendations / Netflix / YouTube
- **Key decisions**: Collaborative filtering vs content-based vs hybrid, embedding models, two-stage (retrieval + ranking), real-time personalization
- **Gotchas**: Cold start, popularity bias, diversity vs relevance

### 2. Search Ranking
- **Context**: Google Search / Amazon Product Search
- **Key decisions**: Query understanding, retrieval (inverted index + ANN), learning-to-rank (LambdaMART, BERT re-ranker), multi-stage ranking
- **Gotchas**: Latency constraints, freshness vs relevance, position bias in training data

### 3. Fraud Detection
- **Context**: Real-time payment fraud / account takeover
- **Key decisions**: Extreme class imbalance, real-time scoring (<100ms), feature velocity, graph-based features
- **Gotchas**: Adversarial adaptation, false positive cost, concept drift

### 4. Content Moderation
- **Context**: Meta/YouTube/Twitter content safety
- **Key decisions**: Multi-modal (text + image + video), multi-label classification, human-in-the-loop, appeals flow
- **Gotchas**: Latency at scale (millions of posts/hour), evolving policies, cultural context

### 5. Ad Click Prediction
- **Context**: Meta News Feed / Google Ads
- **Key decisions**: Feature interactions (DeepFM, DCN), real-time serving, bidding strategy, calibration
- **Gotchas**: Data freshness, feedback delay, exploration vs exploitation

### 6. Conversational AI / RAG Chatbot
- **Context**: Amazon Rufus / Google Bard / Customer service bot
- **Key decisions**: RAG vs fine-tuning, multi-turn memory, tool use, guardrails, evaluation
- **Gotchas**: Hallucination, latency, context window limits, safety

### 7. Demand Forecasting
- **Context**: Amazon logistics / Uber surge pricing
- **Key decisions**: Time series models, feature engineering (holidays, events), hierarchical forecasting, uncertainty quantification
- **Gotchas**: Non-stationarity, rare events (Black Friday), cold start for new products

### 8. Spam / Abuse Detection
- **Context**: Email spam / review fraud / bot detection
- **Key decisions**: Text features + behavioral features + graph features, ensemble approach, adversarial robustness
- **Gotchas**: Arms race with spammers, high precision requirement, low latency

---

## Coding Interview Prep

### LeetCode Strategy

| Phase | Problems/Day | Focus | Total |
|---|---|---|---|
| Weeks 1–10 | 2/day | Easy → Medium (arrays, strings, hashmaps) | 100 |
| Weeks 11–20 | 2–3/day | Medium (trees, graphs, DP, sliding window) | 140 |
| Weeks 21–24 | 3/day | Medium + Hard (DP, graphs, greedy) | 84 |
| **Total** | | | **~300+** |

### Must-Do Lists
1. [NeetCode 150](https://neetcode.io/practice) — structured by pattern
2. [Blind 75](https://www.teamblind.com/post/New-Year-Gift---Curated-List-of-Top-75-LeetCode-Questions-to-Save-Your-Time-OaM1orEU) — minimum viable set
3. [Grind 75](https://www.techinterviewhandbook.org/grind75) — customizable by time

### ML-Specific Coding Questions
These come up in Amazon/Google "applied ML coding" rounds:

- Implement softmax (numerically stable)
- Implement cross-entropy loss
- Implement batch normalization (forward + backward)
- Implement K-Means from scratch
- Implement gradient descent for logistic regression
- Implement a decision tree split criterion
- Implement attention mechanism
- Implement beam search
- Implement precision/recall/F1 from scratch
- Implement TF-IDF from scratch

---

## Behavioral Prep (Critical for Amazon)

### Amazon Leadership Principles — Write STAR Stories

You need 2–3 stories per LP. Format: **Situation → Task → Action → Result**

| LP | Example Question |
|---|---|
| Customer Obsession | "Tell me about a time you went above and beyond for a customer" |
| Ownership | "Tell me about a time you took on something outside your area" |
| Invent and Simplify | "Tell me about a time you found a simple solution to a complex problem" |
| Are Right, A Lot | "Tell me about a time you made a decision with incomplete data" |
| Learn and Be Curious | "Tell me about a time you taught yourself something new" |
| Hire and Develop the Best | "Tell me about a time you mentored someone" |
| Insist on the Highest Standards | "Tell me about a time you refused to compromise on quality" |
| Think Big | "Tell me about a time you proposed a bold idea" |
| Bias for Action | "Tell me about a time you took action without waiting for permission" |
| Frugality | "Tell me about a time you accomplished more with less" |
| Earn Trust | "Tell me about a time you had to deliver difficult feedback" |
| Dive Deep | "Tell me about a time you dug into data to find the root cause" |
| Have Backbone | "Tell me about a time you disagreed with your team/manager" |
| Deliver Results | "Tell me about a time you delivered under a tight deadline" |

### Tips
- Quantify results (reduced latency by 40%, saved $X/month)
- Use recent examples (last 2 years)
- Show technical depth AND business impact
- Practice out loud (record yourself)

---

## Interview Timeline

| When | Action |
|---|---|
| Week 16 | Start applying to warm-up companies (not dream roles) |
| Week 20 | Apply to mid-tier companies for practice |
| Week 22 | Start recruiter outreach at target companies |
| Week 24 | Schedule on-site loops |
| Week 24–28 | Interview sprint (2–3 loops per week) |

### Company Ordering Strategy
1. **Practice**: Smaller companies, startups (low stakes, learn the format)
2. **Mid-tier**: Established companies with ML teams
3. **Target**: FAANG/AI labs (apply after 2+ practice loops)

---

## Resources

| Resource | What It Covers | Cost |
|---|---|---|
| [Chip Huyen: Designing ML Systems](https://www.oreilly.com/library/view/designing-machine-learning/9781098107956/) | End-to-end ML system design | ~$40 |
| [Chip Huyen: ML Interviews Book](https://huyenchip.com/ml-interviews-book/) | Interview prep overview | Free |
| [Exponent](https://tryexponent.com/) | Mock interviews + system design | Paid |
| [InterviewQuery](https://interviewquery.com/) | ML-specific prep | Paid |
| [Made With ML](https://madewithml.com) | Production ML reference | Free |
| [ML System Design (GitHub)](https://github.com/chiphuyen/machine-learning-systems-design) | Design exercises | Free |

---

## 🎯 Phase 6 Completion Criteria

You're ready to interview when you can:
- [ ] Complete any ML system design in 45 minutes (structured, covers all components)
- [ ] Solve LeetCode mediums in under 25 minutes consistently
- [ ] Implement ML algorithms from scratch without reference (logistic regression, attention, KNN)
- [ ] Tell 2–3 compelling STAR stories per Leadership Principle
- [ ] Explain your projects with depth (why decisions were made, what tradeoffs exist)
- [ ] Articulate what you'd do differently with more time/resources
