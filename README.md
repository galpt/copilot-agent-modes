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

## `chatmode-v2.0/`

| File | Target Model |
|------|--------------|
| `aiconf-gpt-4.1.md` | OpenAI GPT-4.1 |
| `aiconf-gpt-5-mini.md` | OpenAI GPT-5-Mini |
| `aiconf-grok-code-fast.md` | Grok Code Fast |
| `aiconf-sonnet.md` | Claude Sonnet |

**Version 2.0** builds on v1.0 with significant improvements for autonomous, tool-enabled workflows in VS Code:

### Key Improvements in v2.0:
- **Full Tool Support:** Expanded tools list to include all VS Code capabilities (terminal selection, test files, search results, codebase navigation, etc.)
- **Autonomous Execution:** Enhanced agent behavior to work continuously until problems are fully solved, only yielding when complete
- **Internet Research:** Integrated web fetching and recursive link gathering for up-to-date documentation and dependency research
- **Enhanced Verification:** Automatic lint checks, test execution, and error reporting after code changes
- **Resume Capability:** Explicit support for "resume" or "continue" commands to pick up from the last incomplete todo item
- **Tool-First Approach:** Stronger emphasis on using VS Code tools for all operations (editing, testing, debugging) rather than manual steps
- **Iterative Problem-Solving:** Built-in workflow for testing edge cases, debugging root causes, and validating solutions rigorously

**When to use v2.0:** If you need autonomous problem-solving with extensive research, rigorous testing, and minimal manual intervention, use v2.0. If you prefer more frequent check-ins and explicit approval at each step, stick with v1.0.



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

1. **Choose the version** that matches your workflow:
   - **v1.0** for collaborative, step-by-step approval at each task
   - **v2.0** for autonomous, tool-enabled problem-solving with minimal intervention

2. **Select the prompt file** that corresponds to your LLM model:
   - Using OpenAI GPT-4.1? → `aiconf-gpt-4.1.md`
   - Using OpenAI GPT-5-Mini? → `aiconf-gpt-5-mini.md`
   - Using Grok Code Fast? → `aiconf-grok-code-fast.md`
   - Using Claude Sonnet? → `aiconf-sonnet.md`

3. **Load it as a system prompt** in your GitHub Copilot chatmode configuration

4. **Start your session** by providing a `session_state` summary containing:
   - High-level goal
   - Approved specification
   - Implementation plan
   - Current progress

5. **Follow the workflow** outlined in the prompt for consistent, spec-driven development

> [!NOTE]
> Version 2.0 is optimized for autonomous workflows and represents a significant evolution from v1.0. Future versions (v3.0+) will continue to refine and improve based on real-world usage.



# License

These files are provided as-is, with no warranty. Use them however you'd like, responsibly.