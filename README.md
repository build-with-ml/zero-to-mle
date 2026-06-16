# 🚀 MLE Roadmap: From Software Engineer to Machine Learning Engineer

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)

A structured, week-by-week roadmap for experienced programmers transitioning to Machine Learning Engineering roles at top AI companies (Amazon, Meta, Google, OpenAI, Anthropic).

> **Built by an engineer, for engineers.** No fluff, no theory-only paths — every week produces code, a blog post, or a deployed artifact.

---

## 🎯 Who This Is For

- Software engineers with 2+ years of programming experience
- Developers who want to transition into MLE roles at FAANG/AI companies
- People who learn by building, not just watching lectures
- Anyone who wants to build an online presence while learning

## 🏗️ What Makes This Different

| Traditional Courses | This Roadmap |
|---|---|
| Learn theory in isolation | Build + publish every week |
| No career visibility | Blog + GitHub + LinkedIn integrated into every phase |
| Generic curriculum | Aligned to actual job descriptions at Amazon, Meta, Google, OpenAI, Anthropic |
| Notebook-only projects | End-to-end: train → deploy → monitor → blog about it |

---

## 📋 Roadmap Overview

| Phase | Weeks | Focus | Key Output |
|---|---|---|---|
| [Phase 1](weeks/phase-1-foundations/) | 1–4 | Math Foundations | Blog series + NumPy implementations |
| [Phase 2](weeks/phase-2-core-ml/) | 5–10 | Core ML Algorithms | Kaggle competition + project repo |
| [Phase 3](weeks/phase-3-deep-learning/) | 11–16 | Deep Learning & Transformers | "Built GPT from scratch" post |
| [Phase 4](weeks/phase-4-llms/) | 17–20 | LLMs, RAG, Fine-tuning, Agents | Deployed LLM app + HuggingFace model |
| [Phase 5](weeks/phase-5-mlops/) | 21–23 | MLOps & Production ML | Full pipeline (flagship project) |
| [Phase 6](weeks/phase-6-interview/) | 24+ | System Design & Interview Prep | Mock interviews + design blog series |

---

## 🏢 Target Roles & What They Actually Test

| Company | Role | Interview Rounds | Key Surprise |
|---|---|---|---|
| **Amazon** | MLE L5/L6 | 7 rounds: OA, HR, 2 coding, 2 system design, behavioral | 2 rounds feel like pure SDE (API design, retry logic) |
| **Meta** | MLE E4/E5 | 5–6 rounds: coding, ML fundamentals, ML system design, behavioral | "Own the whole ML lifecycle" — shipping > theory |
| **Google** | MLE L4/L5 | 5 rounds: coding (×2), ML system design, general system design, behavioral | Coding matters as much as ML knowledge |
| **OpenAI** | MLE | 5–6 rounds: coding, ML depth, system design, research taste | PyTorch + distributed training on H100s |
| **Anthropic** | MLE | 5–6 rounds: systems, ML depth, coding, culture fit | RLHF pipelines + safety/alignment focus |

### Skills Matrix

```
                    Amazon  Meta  Google  OpenAI  Anthropic
DSA + Clean Code     ★★★★★  ★★★★★  ★★★★★   ★★★★    ★★★★
ML Fundamentals      ★★★★★  ★★★★★  ★★★★★   ★★★★★   ★★★★★
ML System Design     ★★★★★  ★★★★★  ★★★★★   ★★★★    ★★★★
Deep Learning        ★★★★   ★★★★★  ★★★★★   ★★★★★   ★★★★★
LLMs & GenAI         ★★★★★  ★★★★   ★★★★★   ★★★★★   ★★★★★
Production/MLOps     ★★★★★  ★★★★   ★★★★    ★★★★★   ★★★★★
Distributed Systems  ★★★★   ★★★★   ★★★★★   ★★★★★   ★★★★★
Behavioral/LPs       ★★★★★  ★★★★   ★★★     ★★★     ★★★
```

---

## 📚 One Resource Per Category (No Decision Fatigue)

| Category | Primary Resource | Cost |
|---|---|---|
| **End-to-End MLOps** | [Made With ML](https://madewithml.com) | Free |
| **Deep Learning** | [Fast.ai](https://course.fast.ai) + [Karpathy Zero to Hero](https://www.youtube.com/playlist?list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhRvKZ) | Free |
| **LLMs** | [HuggingFace LLM Course](https://huggingface.co/learn/llm-course/chapter1/1) | Free |
| **Core ML** | [ML Zoomcamp (DataTalksClub)](https://github.com/DataTalksClub/machine-learning-zoomcamp) | Free |
| **Math Visuals** | [3Blue1Brown](https://www.youtube.com/c/3blue1brown) + [StatQuest](https://www.youtube.com/c/joshstarmer) | Free |
| **MLOps** | [MLOps Zoomcamp](https://github.com/DataTalksClub/mlops-zoomcamp) | Free |
| **System Design** | [Chip Huyen — Designing ML Systems](https://www.oreilly.com/library/view/designing-machine-learning/9781098107956/) + [Free Interview Book](https://huyenchip.com/ml-interviews-book/) | Book ~$40 |
| **Coding** | [NeetCode 150](https://neetcode.io/practice) / LeetCode | Free/Freemium |
| **Behavioral** | Amazon Leadership Principles (write STAR stories) | Free |

---

## 🌐 Online Visibility Strategy

Building in public is not optional — it's your unfair advantage.

### Platforms

| Platform | Purpose | Cadence |
|---|---|---|
| GitHub | Code portfolio | Daily commits |
| Blog (Hashnode/Dev.to) | Technical writing | Every 2 weeks |
| LinkedIn | Career visibility | 2–3 posts/week |
| Twitter/X | Community engagement | Daily |
| HuggingFace | Model demos | Monthly |

### Content That Gets Engagement (Ranked)

1. 🎬 **Visual explainers** (animated GIFs of algorithms)
2. 🔨 **"I built X from scratch"** posts with code
3. 📊 **Benchmark comparisons** ("LoRA vs QLoRA — my results")
4. 🚀 **Live demos** with clickable links
5. 💀 **Failure posts** ("What I got wrong about X")
6. 📈 **Journey updates** ("Month 3 of my MLE transition")

---

## 📁 Repository Structure

```
mle-roadmap/
├── README.md                    ← You are here
├── PROGRESS.md                  ← Track your weekly progress
├── CONTRIBUTING.md              ← How to contribute
├── weeks/
│   ├── phase-1-foundations/     ← Weeks 1–4: Math
│   ├── phase-2-core-ml/        ← Weeks 5–10: Algorithms
│   ├── phase-3-deep-learning/  ← Weeks 11–16: Neural Nets & Transformers
│   ├── phase-4-llms/           ← Weeks 17–20: LLMs, RAG, Agents
│   ├── phase-5-mlops/          ← Weeks 21–23: Production ML
│   └── phase-6-interview/      ← Week 24+: System Design & Prep
├── projects/
│   ├── project-1-ml-pipeline/  ← End-to-end sklearn project
│   ├── project-2-deep-learning/← Fine-tuned model
│   ├── project-3-llm-app/      ← RAG or Agent system
│   └── project-4-mlops/        ← Full production pipeline
├── resources/
│   ├── books.md                ← Recommended books
│   ├── courses.md              ← All courses referenced
│   ├── papers.md               ← Key papers to read
│   └── tools.md                ← Tools & frameworks
└── tracking/
    ├── leetcode-log.md         ← Problem tracking
    ├── blog-tracker.md         ← Published content log
    └── interview-prep.md       ← Mock interview notes
```

---

## 🗓️ Weekly Rhythm

| Day | Activity | Time |
|---|---|---|
| Mon–Fri | Learn (video/reading) + Code practice | 2–3 hrs |
| Mon–Fri | LeetCode | 30–45 min |
| Saturday | Project work + write blog draft | 3–4 hrs |
| Sunday | Publish blog, push code, LinkedIn post | 1–2 hrs |

**Total: ~20–25 hrs/week** (adjustable based on your schedule)

---

## ✅ End-of-Roadmap Checklist

By week 24, you should have:

- [ ] 10+ polished GitHub repos with clean READMEs
- [ ] 12+ technical blog posts
- [ ] 2–3 deployed ML applications
- [ ] 1 end-to-end MLOps pipeline
- [ ] 1 fine-tuned LLM with model card
- [ ] 150+ LeetCode problems solved
- [ ] 8+ ML system designs practiced
- [ ] Active online presence with engagement
- [ ] Ready for FAANG MLE interview loops

---

## 🤝 Contributing

Found a better resource? Have a correction? Built something cool following this roadmap? 

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## ⭐ Star This Repo

If this helps you, star it so others can find it. Share your progress with the hashtag **#MLERoadmap**.

---

## 📄 License

MIT — use it, fork it, share it.
