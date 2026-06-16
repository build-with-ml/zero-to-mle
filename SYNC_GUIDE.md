# 🔄 Keeping Your Fork Up to Date

When you fork `zero-to-mle`, you get your own copy. But the original repo keeps growing — new Q&A, better resources, fixes. Here's how to pull those updates **without losing your progress**.

---

## The Golden Rule

> **Only edit files in `tracking/` and `projects/`** — these are YOUR personal files.
> 
> Everything else (`weeks/`, `resources/`, `qa/`, `README.md`) belongs to the upstream repo and will receive updates.

### What's Safe to Edit (YOUR files)

```
✅ tracking/leetcode-log.md       ← Your LeetCode progress
✅ tracking/blog-tracker.md       ← Your published posts
✅ tracking/interview-prep.md     ← Your interview notes
✅ PROGRESS.md                    ← Your checkboxes
✅ projects/*/                    ← Your actual project code
✅ Any new files you create       ← Your notes, experiments, etc.
```

### What Gets Updated from Upstream (DON'T edit these)

```
⚠️ weeks/*/README.md             ← Updated with new content, fixes
⚠️ weeks/*/qa-*.md               ← Community Q&A (growing over time)
⚠️ resources/                    ← New books, courses, tools
⚠️ README.md                     ← Improved instructions, links
⚠️ QA_GUIDE.md                   ← Updated Q&A guidelines
⚠️ CONTRIBUTING.md               ← Updated guidelines
```

---

## How to Sync (2 Methods)

### Method 1: GitHub UI (Easiest)

1. Go to **your fork** on GitHub
2. You'll see a banner: "This branch is X commits behind upstream"
3. Click **"Sync fork"** → **"Update branch"**
4. Done! No conflicts because you only edited `tracking/` and `projects/`

### Method 2: Command Line

```bash
# One-time setup: add the original repo as "upstream"
git remote add upstream https://github.com/build-with-ml/zero-to-mle.git

# Whenever you want to pull new content:
git fetch upstream
git merge upstream/main

# Push the merged updates to YOUR fork
git push origin main
```

**If you get merge conflicts** (because you edited a shared file):
```bash
# Accept upstream's version for shared files
git checkout --theirs weeks/ resources/ README.md QA_GUIDE.md
git add .
git commit -m "sync: merge upstream updates, keep my tracking"
```

---

## Recommended Workflow

```
Week N:
1. Learn from weeks/phase-X/README.md (DON'T edit this)
2. Ask questions → add to weeks/phase-X/qa-*.md (contribute via PR later)
3. Write your notes in tracking/ or a personal notes/ folder (yours to edit)
4. Check off items in PROGRESS.md (yours to edit)
5. Build projects in projects/ (yours to edit)
6. Periodically PR your best Q&A entries back to upstream
7. Sync from upstream every 1-2 weeks to get new Q&A from others
```

---

## FAQ

**Q: What if I accidentally edited a shared file?**  
A: When you sync, you'll get a merge conflict. Resolve it by accepting the upstream version (`git checkout --theirs <file>`), then move your notes to `tracking/` or a personal file.

**Q: How often should I sync?**  
A: Every 1–2 weeks, or whenever you see the "X commits behind" banner on GitHub.

**Q: Can I add my own folders?**  
A: Yes! Create any personal folders (e.g., `my-notes/`, `experiments/`). These won't conflict with upstream since they don't exist there.

**Q: What if I want to contribute back?**  
A: Great! Create a PR from your fork to the upstream repo. See [CONTRIBUTING.md](CONTRIBUTING.md).
