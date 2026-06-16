<p align="center">
  <img src="https://img.shields.io/badge/Duration-24_Weeks-blue?style=for-the-badge" alt="Duration"/>
  <img src="https://img.shields.io/badge/Cost-Free-green?style=for-the-badge" alt="Cost"/>
  <img src="https://img.shields.io/badge/Target-FAANG_&_AI_Labs-red?style=for-the-badge" alt="Target"/>
</p>

# 🧠 Zero to MLE

**The open-source, week-by-week roadmap to become a Machine Learning Engineer at top AI companies.**

From SWE → MLE at Amazon, Meta, Google, OpenAI, or Anthropic in 24 weeks — with code, blogs, and a public portfolio built along the way.

<p align="center">
  <a href="#-quick-start">Quick Start</a> •
  <a href="#-who-this-is-for">Who It's For</a> •
  <a href="#-roadmap-overview">Roadmap</a> •
  <a href="#-how-to-use-this-repo">How to Use</a> •
  <a href="#-resources">Resources</a> •
  <a href="#-contributing">Contributing</a>
</p>

---

## ⚡ Quick Start

```bash
# 1. Fork this repo (click "Fork" button above) — this gives you your own copy to track progress
# 2. Clone YOUR fork
git clone https://github.com/YOUR_USERNAME/zero-to-mle.git
cd zero-to-mle

# 3. Start with Phase 1
open weeks/phase-1-foundations/README.md

# 4. Track progress in PROGRESS.md — check off items as you go
# 5. Push your progress to YOUR fork (keeps your GitHub green!)
```

> **Why fork?** You'll check off tasks, add your own notes, push project code, and build your contribution graph — all in your own copy. The original repo stays clean for others.

---

## 🎯 Who This Is For

- ✅ Software engineers (2+ years coding) who want to become MLEs
- ✅ People who learn by **building**, not just watching
- ✅ Anyone who wants to build an **online presence** while learning
- ✅ Developers targeting roles at Amazon, Meta, Google, OpenAI, Anthropic

**Not for you if:**
- ❌ You're brand new to programming (learn Python first)
- ❌ You want theory-only academic path (this is production-focused)
- ❌ You're looking for a quick 2-week crash course

---

## 🏗️ What Makes This Different

| Traditional Courses | Zero to MLE |
|---|---|
| Learn theory in isolation | **Build + publish every week** |
| No career visibility | Blog + GitHub + LinkedIn integrated into every phase |
| Generic curriculum | **Aligned to actual job descriptions** at Amazon, Meta, Google, OpenAI, Anthropic |
| Notebook-only projects | End-to-end: train → deploy → monitor → blog about it |
| Passive consumption | **Trackable progress** with checkboxes and milestones |
| Human-only content | **Agent-friendly structure** — use with AI coding assistants |

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

Based on 2025–2026 job descriptions and candidate reports:

| Company | Role | Rounds | Key Insight |
|---|---|---|---|
| **Amazon** | MLE L5/L6 | 7: OA, HR, 2 coding, 2 system design, behavioral | 2 rounds feel like pure SDE interviews |
| **Meta** | MLE E4/E5 | 5–6: coding, ML fundamentals, ML system design, behavioral | "Own the whole ML lifecycle" |
| **Google** | MLE L4/L5 | 5: coding ×2, ML system design, system design, behavioral | Coding matters as much as ML |
| **OpenAI** | MLE | 5–6: coding, ML depth, system design, research taste | PyTorch + distributed training |
| **Anthropic** | MLE | 5–6: systems, ML depth, coding, culture | RLHF + safety/alignment focus |

<details>
<summary><b>📊 Skills Matrix (click to expand)</b></summary>

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
</details>

---

## 📖 How to Use This Repo

### Option A: Fork & Track (Recommended)

Best for people following the full roadmap:

1. **Fork** this repo (top-right "Fork" button)
2. **Clone** your fork locally
3. Open `PROGRESS.md` and check off items as you complete them
4. Create project folders under `projects/` for your actual code
5. Push regularly — builds your GitHub contribution graph
6. Your fork becomes your learning portfolio

### Option B: Use as Template

If you want a clean starting point without the commit history:

1. Click **"Use this template"** (green button, if enabled)
2. Name your new repo (e.g., `my-mle-journey`)
3. Start fresh with your own commits

### Option C: Reference Only

Just reading and picking resources:
- Browse the weekly plans in `weeks/`
- Check resource lists in `resources/`
- No need to clone — read directly on GitHub

### Using with AI Coding Assistants 🤖

This repo is structured to work well with AI agents (Kiro, Copilot, Cursor, etc.):

- **Ask your AI assistant to read a week's plan**: "Read `weeks/phase-3-deep-learning/README.md` and help me implement this week's exercises"
- **Use project templates as specs**: "Follow the structure in `projects/project-3-llm-app/README.md` to scaffold my RAG project"
- **Track progress with AI help**: "Read `PROGRESS.md` and tell me what I should work on next"
- **Auto-extract Q&A**: After a study session, ask your AI: "Summarize the key questions I asked today in the Q&A format from `qa/README.md` and add them to the relevant phase file"
- **The flat markdown structure** makes it easy for LLMs to parse and reason about

### Keeping Your Fork Updated 🔄

The main repo grows over time (new Q&A, better resources, fixes). See **[SYNC_GUIDE.md](SYNC_GUIDE.md)** for how to pull updates without losing your progress.

**TL;DR**: Only edit files in `tracking/`, `projects/`, and `PROGRESS.md`. Everything else syncs cleanly from upstream.

### Contributing Q&A Back 🧠

As you learn, you'll ask great questions. Add them to `qa-*.md` files in the same phase folder, then PR the best ones back. See **[QA_GUIDE.md](QA_GUIDE.md)** for format and workflow.

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
| **Coding** | [NeetCode 150](https://neetcode.io/practice) / LeetCode | Free |

Full lists: [📖 Books](resources/books.md) • [📺 Courses](resources/courses.md) • [📄 Papers](resources/papers.md) • [🛠️ Tools](resources/tools.md)

---

## 🌐 Online Visibility Strategy

Building in public is not optional — it's your unfair advantage.

| Platform | Purpose | Cadence |
|---|---|---|
| GitHub | Code portfolio + contribution graph | Daily commits |
| Blog (Hashnode/Dev.to) | Technical writing | Every 2 weeks |
| LinkedIn | Career visibility + networking | 2–3 posts/week |
| Twitter/X | Community engagement | Daily |
| HuggingFace | Model demos + Spaces | Monthly |

### Content That Gets Engagement

1. 🎬 **Visual explainers** (animated GIFs of algorithms)
2. 🔨 **"I built X from scratch"** posts with code
3. 📊 **Benchmark comparisons** ("LoRA vs QLoRA — my results")
4. 🚀 **Live demos** with clickable links
5. 💀 **Failure posts** ("What I got wrong about X")

---

## 🗓️ Weekly Rhythm

| Day | Activity | Time |
|---|---|---|
| Mon–Fri | Learn (video/reading) + Code | 2–3 hrs |
| Mon–Fri | LeetCode | 30–45 min |
| Saturday | Project work + blog draft | 3–4 hrs |
| Sunday | Publish blog, push code, LinkedIn post | 1–2 hrs |

**Total: ~20–25 hrs/week** (adjustable for your schedule)

---

## 📁 Repository Structure

```
zero-to-mle/
├── README.md                    ← You are here
├── PROGRESS.md                  ← ✅ Track your weekly progress (YOUR file)
├── SYNC_GUIDE.md                ← How to pull updates without losing progress
├── CONTRIBUTING.md              ← How to contribute
├── CODE_OF_CONDUCT.md           ← Community standards
├── LICENSE                      ← MIT
├── QA_GUIDE.md                  ← 🧠 How the Q&A system works
├── weeks/
│   ├── phase-1-foundations/     ← Weeks 1–4: Math + qa-*.md files
│   ├── phase-2-core-ml/        ← Weeks 5–10: Algorithms + qa-*.md files
│   ├── phase-3-deep-learning/  ← Weeks 11–16: Neural Nets + qa-*.md files
│   ├── phase-4-llms/           ← Weeks 17–20: LLMs + qa-*.md files
│   ├── phase-5-mlops/          ← Weeks 21–23: Production ML + qa-*.md files
│   └── phase-6-interview/      ← Week 24+: System Design + qa-*.md files
├── projects/
│   ├── project-1-ml-pipeline/  ← End-to-end sklearn project
│   ├── project-2-deep-learning/← Fine-tuned model
│   ├── project-3-llm-app/      ← RAG or Agent system
│   └── project-4-mlops/        ← Full production pipeline (capstone)
├── resources/
│   ├── books.md                ← Recommended books
│   ├── courses.md              ← All courses with links
│   ├── papers.md               ← Key papers to read
│   └── tools.md                ← Tools & frameworks
└── tracking/
    ├── leetcode-log.md         ← Problem tracking
    ├── blog-tracker.md         ← Content pipeline
    └── interview-prep.md       ← Mock interviews & applications
```

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

Found a better resource? Fixed a broken link? Built something cool following this roadmap?

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

**Ways to contribute:**
- 🔗 Add or update resources
- 🐛 Fix errors or broken links
- 💡 Share your experience (what worked, what didn't)
- 📝 Add interview questions you encountered
- 🎨 Improve visualizations or diagrams

---

## 🌟 Star History

If this helps you, **star it** ⭐ so others can find it.

Share your progress with **#ZeroToMLE** on Twitter/LinkedIn.

---

## 📄 License

[MIT](LICENSE) — use it, fork it, share it, improve it.

---

<p align="center">
  <b>Built with 🧠 by <a href="https://github.com/build-with-ml">build-with-ml</a></b><br/>
  <i>If this roadmap helps you land an MLE role, consider starring the repo and sharing your story!</i>
</p>
