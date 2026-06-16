# Contributing to Zero to MLE

Thanks for your interest in improving this roadmap! Here's how you can help.

---

## Ways to Contribute

### 1. 🧠 Add Q&A (Most Valuable!)

The Q&A files (`qa-*.md`) in each phase folder are the **community knowledge base**. They grow as people learn.

**How to contribute Q&A:**

1. Find the right file: `weeks/phase-X/qa-[topic].md`
2. Add your entry at the bottom (before the comment block)
3. Use the standard format:
   ```markdown
   ### Q: [Your question]
   
   **Context**: [When/why this came up]
   
   **Answer**: 
   [Clear explanation]
   
   **Key Insight**: [One-line takeaway]
   
   **Tags**: `#topic` `#interview-relevant`
   ```
4. Submit a PR with title: `qa(phase-X): Add N questions on [topic]`

**What makes good Q&A:**
- ✅ Concepts that confused you
- ✅ "Why" questions (not just "what")
- ✅ Interview questions you encountered
- ✅ Misconceptions that were corrected
- ✅ Connections between topics
- ❌ One-word-answer questions (too simple)
- ❌ Debugging issues (too specific)

See [QA_GUIDE.md](QA_GUIDE.md) for the full guide.

---

### 2. 🔗 Fix Errors or Broken Links

- Found a dead link? Submit a PR with the updated URL.
- Found incorrect information? Open an issue with the correction.

---

### 3. 📚 Suggest Better Resources

Found a resource better than what's listed? Open a PR with:
- The resource URL
- Why it's better (more current, more practical, better explained)
- Which week/phase it belongs to

**Guidelines for resources:**
- Must be free or low-cost (accessibility matters)
- Must be current (updated within last 2 years)
- Prefer code-first, project-based over theory-only
- Include target company relevance if interview-related

---

### 4. 🎉 Share Your Journey

Used this roadmap? Share what worked:
- Open a [Journey Discussion](../../discussions) or Issue
- Include: timeline, adjustments you made, results
- Help others by sharing what was harder/easier than expected

---

### 5. 🆕 Add New Q&A Topic Files

If a topic doesn't have a Q&A file yet, create one:
- File naming: `qa-[topic-name].md` (kebab-case)
- Place in the relevant phase folder
- Start with the header template:
  ```markdown
  # ❓ Q&A: [Topic Name] (Week N)
  
  Questions and answers collected during study.
  
  ---
  ```

---

## PR Guidelines

### Title Format

| Type | Format | Example |
|---|---|---|
| Q&A | `qa(phase-X): description` | `qa(phase-3): Add 4 questions on attention mechanism` |
| Resource | `resource(phase-X): description` | `resource(phase-4): Update HuggingFace course link` |
| Fix | `fix: description` | `fix: Broken StatQuest link in phase-1` |
| Content | `content(phase-X): description` | `content(phase-2): Add SHAP explanation to week 6` |

### PR Body Template

```markdown
## What this changes
[Brief description]

## Why
[Why this improvement matters]

## Phase/Week affected
[Which section this modifies]

## Checklist
- [ ] Follows Q&A format (if adding Q&A)
- [ ] Links are valid and accessible
- [ ] Content is accurate (to best of my knowledge)
- [ ] No personal tracking data included
```

---

## What NOT to Contribute

- ❌ Changes to `PROGRESS.md` (that's personal per fork)
- ❌ Changes to `tracking/` files (personal per fork)
- ❌ Project code in `projects/` (personal per fork)
- ❌ Paid resources behind paywalls (keep it accessible)
- ❌ AI-generated content without review (must be verified for accuracy)
- ❌ Company-confidential interview questions (no NDA violations)

---

## Fork vs Upstream: What Goes Where?

| Content Type | Where it lives | Who edits |
|---|---|---|
| Weekly plans | `weeks/phase-X/README.md` | Upstream (via PR) |
| Q&A knowledge | `weeks/phase-X/qa-*.md` | Upstream (via PR) |
| Resources | `resources/*.md` | Upstream (via PR) |
| Your progress | `PROGRESS.md` | Your fork only |
| Your projects | `projects/*/` | Your fork only |
| Your tracking | `tracking/*.md` | Your fork only |

---

## Code of Conduct

Be respectful, be helpful, be kind. We're all on the same journey. See [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).
