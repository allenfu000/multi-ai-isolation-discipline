# Engineering Discipline for Physically Isolated Multi-AI Collaboration

> *The author's native language is Chinese. This English version was translated by AI with the goal of preserving the original meaning as faithfully as possible.*

## Who This Is For

- People using two or more AI products at the same time (Claude / ChatGPT / Codex, etc.)
- People who want to use multi-AI cross-checking to reduce model bias

## Core Principle

**The information flow between two or more AIs across your entire computer must be strictly separated by the human brain. AIs must not share any content with each other, directly or indirectly.**

If this principle is violated, all "multi-AI collaboration" will eventually converge and lose its cross-checking value.

(For example, with tasks like data API collection: you must have different AIs collect data separately and one at a time — even if it's the exact same data. Accept the time cost.)

---

## 1. Isolation

- **Two independent root directories**: `claude-projects\` and `codex-projects\`. Every project belongs to one AI permanently. Never cross root directories.
- **Desktop app icons, terminals, and shortcuts physically separated** — so you are clearly aware of which AI's workflow you are entering.
- **Do not create any shared folder, including read-only shares.**
- **Projects must not be handed off across AIs. Switching AIs requires redoing the proposal from scratch!** Once the receiving AI reads the original proposal, it is locked in. From that point on, it can only make local modifications inside the original framework — it cannot produce an independent perspective or independent characteristics.
- **The source of any proposal must always come from a single AI's product line, kept in a closed loop, with parallel proposals built on both sides separately** — when launching a Codex project, go talk to ChatGPT (web) for an independent proposal; when launching a Claude Code project, go talk to Claude (web) for an independent proposal. **The two AIs must never communicate with each other directly.**

---

## 2. Audit Workflow

| Step | Action | Key Discipline |
|---|---|---|
| 1 | Claude and Codex each finish their work in fully isolated environments (fully completed, not mid-way). | Half-finished work cannot be audited. With a half-finished project, you cannot tell whether a "problem" is a bug or just unfinished work. |
| 2 | Copy Codex's complete output **as-is into a brand new, independent desktop folder**. | A clean folder that has never held anything before. |
| 3 | In this new folder, launch **a new Claude window** (not the original Claude window). | A new window means no inherited context from the original Claude — it exists purely to translate. |
| 4 | Have the new Claude window **translate Codex's output into Claude-style — pure translator role, only style changes, no judgment whatsoever.** | Strictly preserve the original engineering and code logic. Only change directory layout, naming, library choices, and other non-foundational stylistic elements. **Completely ignore** anything it thinks is wrong — just produce a "Claude-style version." |
| 5 | Have the **original Claude window** compare the "translated version" against its own version, and point out the underlying logical differences. | The original Claude window is the only auditor. The new Claude window must never participate in the audit. |
| 6 | The human brain acts as **secondary auditor**: fill in anything the original window may have missed, then decide which suggestions to absorb and how to apply them. | The human brain is not a passive receiver of the AI's audit results — it references them and patches the gaps. |

---

**Why translation is mandatory**:

When you directly compare raw Codex output ↔ raw Claude output, the differences are a mix of two things:

- **Style differences** (naming habits, structural preferences, library choices) — this is **noise**
- **Underlying logic differences** (genuine disagreement on how to handle the same problem) — this is **signal**

**Without the translation step, you just end up hunting for the other side's noise** — and most of the "problems" you find are just stylistic differences, not real disagreements. After translation, the two outputs share a unified style, and **what's left is the real question worth digging into.**

---

**Why the new Claude window must be a pure translator and must not flag problems**:

During translation, the new Claude window's default tendency is to "fix" whatever it thinks Codex got wrong. Once it starts making judgments, **the final audit authority gets split between two Claude windows, and the cross-check mechanism breaks down.**

Even worse: if the new Claude window directly modifies the engineering, that output is now Claude's *takeover version* — it no longer carries Codex's logic. **The project has effectively been merged, and the dual-AI cross-check is destroyed entirely.**

Roles must be unambiguous:

- **New Claude window = Pure translator** (only style changes, completely ignores anything it thinks is a problem)
- **Original Claude window = The only auditor** (looks at the two style-unified versions and points out underlying logical disagreements)
- **Human brain = Secondary auditor** (references the original window's audit + fills in what it missed + makes the final decision)

---

## Side Notes

**Non-programmers, be cautious with high-execution-power AIs like Codex.** When your instructions are ambiguous, it will spiral with you — humans and AI looping efficiently down the wrong path together. Non-programmers find this very hard to detect, because Codex's primary objective is strong execution and rigorous in-scope delivery. (Non-programmer enters rigorous spiral mode.)

**When using critical-mode Claude, hold your main line.** Logic can never be "perfect." It's easy to fall into infinitely surfacing problems and infinitely revising the main line — and then the project never reaches completion. This happens because Claude's primary objective is strong collaboration and clear in-scope execution; it will keep digging deeper with you. (Non-programmer enters spiral-fix mode.)

I have no programming background. The whole thing above is just me talking shit. Take it for what it's worth.

---

**Author**: allenfu000
**Translation note**: The author's native language is Chinese. This English version was translated by AI with the goal of preserving the original meaning as faithfully as possible.
**Methodology source**: All methodology comes from the author's own practice. Text structuring assisted by Claude Opus 4.7.
**Version**: 2026-05-09 v1
