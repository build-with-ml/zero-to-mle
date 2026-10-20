---
id: q-0001-what-is-compiled-code
title: What does "compiled C/Fortran code" mean?
kind: fork
concepts: [compiled-code, portability]
entry_point: false
parent_anchor:
  node: env-00-why-not-share-venv
  text: "compiled C/Fortran code"
question: "(implied) what is compiled code, and why is it platform-specific?"
related: [env-00-why-not-share-venv]
source_session: 2026-10-20
---

# What does "compiled C/Fortran code" mean?

## Context

numpy is fast because its heavy math isn't written in Python — it's written in C
and Fortran and **compiled**.

## Hooks

- Python code runs the same on Mac, Windows, Linux. Why wouldn't compiled code?
- What exactly is produced when you "compile" something?

## Answer

**Compiling** = translating human-readable source code into the raw instructions a
specific CPU understands (machine code). Those instructions are tied to:

- the **CPU family** (Apple Silicon/arm64 vs Intel/x86 speak different machine code), and
- the **operating system** (macOS, Windows, Linux package and load binaries differently).

So a numpy compiled for macOS-arm64 is a `.so` file full of arm64-mac machine code.
Run it on Windows-x86 and the instructions are meaningless there — hence the
architecture-mismatch error.

Plain Python files (`.py`) are *not* compiled ahead of time — they're interpreted
line by line at runtime, which is why they run anywhere but are slower. numpy trades
that portability for speed by shipping precompiled binaries, one build per platform.

## Next

- Back to: **env-00** — why this makes `.venv` unshareable.
- Related: **env-02** — the `.py` files numpy *also* ships are found via `sys.path`.
