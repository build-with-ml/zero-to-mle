---
id: q-0006-what-is-rust
title: What is Rust (and why does it make uv fast)?
kind: fork
concepts: [rust, tooling, compiled-code, uv]
entry_point: false
parent_anchor:
  node: env-01-version-in-import
  text: "Rust-based tool"
question: "Rust-based tool — what is this?"
related: [q-0007-freeze-and-speed, q-0001-what-is-compiled-code]
source_session: 2026-10-20
---

# What is Rust, and why does it make `uv` fast?

## Context

`uv` (the fast installer) is described as "Rust-based". That phrase alone explains
nothing to a newcomer, so here's the content.

## Hooks

- Does "Rust" change *your* code, or the *tool*?
- Why would the language a tool is written in affect how fast it installs packages?

## Answer

**Rust** is a programming language (like Python, Java, C++). The one relevant fact:
Rust **compiles to fast machine code**, in the same speed class as C — far faster
than Python for this kind of work.

It's not about your code — it's about what the *tool* is built in:

- `pip` (the old installer) is **written in Python**, which is slow at installer work
  (checking many version combinations, unzipping).
- `uv` is **written in Rust**, so the installer itself runs much faster, and it also
  downloads packages in parallel.

Analogy: a calculator app written in a fast language adds numbers faster than the
same app in a slow one. `uv` is the fast-language version of `pip`.

## Next

- Related: **q-0007** — the measured speed difference (uv vs pip) and "freeze versions".
- Related: **q-0001** — what "compiles to machine code" means.
