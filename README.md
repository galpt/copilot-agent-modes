# Chatmode Fine-tuning: Spec-driven Copilot Modes

*Pragmatic system prompts for AI agents that value clarity over hype*



# Overview

This repository contains a collection of **chatmode system prompts** designed to guide GitHub Copilot-style agents toward **spec-driven**, **stateful**, and **pragmatic** behavior when working on real software projects.

These prompts intentionally avoid flashy buzzwords and emoji-heavy "vibe coding" instructions. Instead, they focus on established software engineering practices and reproducible workflows that work in professional team environments.



# What's Inside

## `chatmode-v1.0/`

| File | Target Model |
|------|--------------|
| `aiconf-gpt-4.1.md` | OpenAI GPT-4.1 |
| `aiconf-gpt-5-mini.md` | OpenAI GPT-5-Mini |
| `aiconf-grok-code-fast.md` | Grok Code Fast |
| `aiconf-sonnet.md` | Claude Sonnet |

**Version 1.0** is the initial implementation focusing on making these specific LLM models spec-driven rather than using GitHub Copilot's default Agent mode behavior.

All prompts in v1.0 share the same foundation:
- **State synchronization** at the start of every session
- **Spec-driven development** (plan before coding)
- **Collaborative execution** with explicit task tracking
- **Scalability strategies** for handling large codebases



# Why This Exists

Most publicly shared chatmodes lean into dramatic language, excessive emojis, and hyperbolic claims about "superhuman" or "quantum cognitive" workflows. From a developer's perspective — especially those who learned software engineering before the current AI agent craze — that approach can feel gimmicky and unhelpful.

**Real projects need real processes:**
- Clear specifications
- Versioned implementation plans
- Verifiable, reviewable changes
- Proper handover documentation

This repo brings AI agents back to fundamentals: **spec-driven development**, **stateful sessions**, and **practical collaboration**.

## A Note on "Vibe Coding"

I'm not against experimentation or casual coding. The problem emerges when people create chatmodes without understanding software engineering fundamentals, leading to:

- Unmaintainable spaghetti code
- Confusing project histories
- Poor team collaboration
- Projects that can't scale beyond prototypes

If you're building chatmodes for professional or collaborative projects, understanding **Software Development Life Cycle (SDLC)** is essential.

> [!TIP]
> **Recommended reading:** *Software Engineering: A Practitioner's Approach* by Roger S. Pressman



# How to Use These Prompts

1. **Choose the prompt file** that corresponds to your LLM model:
   - Using OpenAI GPT-4.1? → `aiconf-gpt-4.1.md`
   - Using OpenAI GPT-5-Mini? → `aiconf-gpt-5-mini.md`
   - Using Grok Code Fast? → `aiconf-grok-code-fast.md`
   - Using Claude Sonnet? → `aiconf-sonnet.md`

2. **Load it as a system prompt** in your GitHub Copilot chatmode configuration

3. **Start your session** by providing a `session_state` summary containing:
   - High-level goal
   - Approved specification
   - Implementation plan
   - Current progress

4. **Follow the workflow** outlined in the prompt for consistent, spec-driven development

> [!NOTE]
> Version 1.0 represents the first iteration of these spec-driven prompts. Future versions (v2.0+) will include improvements and refinements based on real-world usage.



# License

These files are provided as-is, with no warranty. Use them however you'd like, responsibly.