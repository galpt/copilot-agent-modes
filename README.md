# Chatmode Fine-tuning: Spec-driven Copilot Modes

Pragmatic system prompts for AI agents that value clarity over hype.

## Table of Contents

- [Overview](#overview)
- [What's Inside](#whats-inside)
  - [chatmode-v1.0](#chatmode-v10)
  - [chatmode-v2.0](#chatmode-v20)
  - [chatmode-v3.0](#chatmode-v30)
- [Why This Exists](#why-this-exists)
- [How to Use These Prompts](#how-to-use-these-prompts)
- [Design Philosophy](#design-philosophy)
- [Contributing](#contributing)
- [License](#license)

## Overview

This repository contains a collection of **chatmode system prompts** designed to guide GitHub Copilot-style agents toward **spec-driven**, **stateful**, and **pragmatic** behavior when working on real software projects.

These prompts intentionally avoid flashy buzzwords and emoji-heavy "vibe coding" instructions. Instead, they focus on established software engineering practices and reproducible workflows that work in professional team environments.

## What's Inside

### chatmode-v1.0

**Version 1.0** is the initial implementation focusing on making specific LLM models spec-driven rather than using GitHub Copilot's default Agent mode behavior.

| File | Target Model |
|------|--------------|
| `aiconf-gpt-4.1.md` | OpenAI GPT-4.1 |
| `aiconf-gpt-5-mini.md` | OpenAI GPT-5-Mini |
| `aiconf-grok-code-fast.md` | Grok Code Fast |
| `aiconf-sonnet.md` | Claude Sonnet |

All prompts in v1.0 share the same foundation:
- **State synchronization** at the start of every session
- **Spec-driven development** (plan before coding)
- **Collaborative execution** with explicit task tracking
- **Scalability strategies** for handling large codebases

### chatmode-v2.0

**Version 2.0** builds on v1.0 with significant improvements for autonomous, tool-enabled workflows in VS Code.

| File | Target Model |
|------|--------------|
| `aiconf-gpt-4.1.md` | OpenAI GPT-4.1 |
| `aiconf-gpt-5-mini.md` | OpenAI GPT-5-Mini |
| `aiconf-grok-code-fast.md` | Grok Code Fast |
| `aiconf-sonnet.md` | Claude Sonnet |

Key improvements in v2.0:
- **Full Tool Support:** Expanded tools list to include all VS Code capabilities (terminal selection, test files, search results, codebase navigation, etc.)
- **Autonomous Execution:** Enhanced agent behavior to work continuously until problems are fully solved, only yielding when complete
- **Internet Research:** Integrated web fetching and recursive link gathering for up-to-date documentation and dependency research
- **Enhanced Verification:** Automatic lint checks, test execution, and error reporting after code changes
- **Resume Capability:** Explicit support for "resume" or "continue" commands to pick up from the last incomplete todo item
- **Tool-First Approach:** Stronger emphasis on using VS Code tools for all operations (editing, testing, debugging) rather than manual steps
- **Iterative Problem-Solving:** Built-in workflow for testing edge cases, debugging root causes, and validating solutions rigorously

**When to use v2.0:** If you need autonomous problem-solving with extensive research, rigorous testing, and minimal manual intervention, use v2.0. If you prefer more frequent check-ins and explicit approval at each step, stick with v1.0.

### chatmode-v3.0

**Version 3.0** represents a complete rewrite optimized for specific AI model families, incorporating official prompting best practices from OpenAI and Anthropic.

| File | Target Model Family |
|------|---------------------|
| `gpt-finetuned.md` | OpenAI GPT models (gpt-4.1, gpt-5) |
| `sonnet-finetuned.md` | Anthropic Claude/Sonnet models |

Version 3.0 introduces model-specific optimizations:

#### For OpenAI GPT Models (`gpt-finetuned.md`)
- **OpenAI Prompting Guide Alignment:** Follows OpenAI's GPT-5 prompting recommendations including tool preambles, agentic persistence, and context gathering heuristics
- **Conversation Summaries:** Replaces session_state with dynamic conversation summaries at task start
- **Context Gathering Optimization:** Parallel search strategies with early stop criteria to balance thoroughness and efficiency
- **Tool Preambles:** Clear communication before, during, and after tool usage for better user experience
- **Comprehensive Tool Support:** 40+ VS Code built-in tools including `#fetch`, `#githubRepo`, `#codebase`, `#problems`, and all editing/testing tools

#### For Anthropic Claude/Sonnet Models (`sonnet-finetuned.md`)
- **XML-Structured Thinking:** Extensive use of XML tags (`<thinking>`, `<analysis>`, `<plan>`, `<answer>`) for structured reasoning
- **Chain of Thought (CoT):** Explicit instructions for step-by-step reasoning with visible thought processes
- **Role Prompting:** Clear role definition as seasoned software engineer and architect
- **Prefilling Support:** Guidance on using Anthropic's prefilling feature to skip preambles and control output format
- **Hierarchical XML Tags:** Nested XML structure for all major sections following Anthropic's recommended patterns

#### Common v3.0 Features
- **Beast Mode Philosophy:** Autonomous, action-oriented tone inspired by proven chatmode patterns
- **Mandatory Web Research:** Heavy emphasis on using `#fetch` tool for up-to-date information before any code changes
- **Deprecation Awareness:** Explicit instructions to avoid deprecated APIs (e.g., Go's `ioutil`) and verify current best practices
- **Frontend Defaults:** Tailwind CSS mandatory for all frontend work unless specified otherwise
- **Rigorous Testing:** Multiple test iterations to catch edge cases before considering tasks complete
- **No Session State Files:** Both models use conversation summaries instead of persistent `.session_state` files
- **Tool-First Development:** Prefer VS Code tools over manual steps for all operations

**When to use v3.0:** Use v3.0 when working with modern GPT or Claude models and you want cutting-edge, model-specific optimizations based on official vendor recommendations. v3.0 is recommended for all new projects.

> [!NOTE]
> v3.0 files are named differently (`gpt-finetuned.md` and `sonnet-finetuned.md`) to emphasize they are optimized for specific model families rather than individual model versions.

## Why This Exists

Most publicly shared chatmodes lean into dramatic language, excessive emojis, and hyperbolic claims about "superhuman" or "quantum cognitive" workflows. From a developer's perspective—especially those who learned software engineering before the current AI agent craze—that approach can feel gimmicky and unhelpful.

**Real projects need real processes:**
- Clear specifications
- Versioned implementation plans
- Verifiable, reviewable changes
- Proper handover documentation

This repo brings AI agents back to fundamentals: **spec-driven development**, **stateful sessions**, and **practical collaboration**.

### A Note on "Vibe Coding"

The problem emerges when people create chatmodes without understanding software engineering fundamentals, leading to:

- Unmaintainable spaghetti code
- Confusing project histories
- Poor team collaboration
- Projects that can't scale beyond prototypes

If you're building chatmodes for professional or collaborative projects, understanding **Software Development Life Cycle (SDLC)** is essential.

> [!TIP]
> **Recommended reading**
>
> *Software Engineering: A Practitioner's Approach* by Roger S. Pressman

## How to Use These Prompts

1. **Choose the version** that matches your workflow:
   - **v1.0** for collaborative, step-by-step approval at each task
   - **v2.0** for autonomous, tool-enabled problem-solving with minimal intervention
   - **v3.0** for model-specific optimizations with official vendor best practices (recommended)

2. **Select the prompt file** that corresponds to your AI model:
   - **v3.0 (recommended):**
     - Using OpenAI GPT-4.1 or GPT-5? → `chatmode-v3.0/gpt-finetuned.md`
     - Using Anthropic Claude Sonnet? → `chatmode-v3.0/sonnet-finetuned.md`
   - **v2.0:**
     - `chatmode-v2.0/aiconf-gpt-4.1.md`, `aiconf-gpt-5-mini.md`, `aiconf-grok-code-fast.md`, or `aiconf-sonnet.md`
   - **v1.0:**
     - `chatmode-v1.0/aiconf-gpt-4.1.md`, `aiconf-gpt-5-mini.md`, `aiconf-grok-code-fast.md`, or `aiconf-sonnet.md`

3. **Load it as a custom instruction or system prompt** in your GitHub Copilot chatmode configuration or custom chat mode settings

4. **Start your session:**
   - **v3.0:** Simply start working—the model will synthesize conversation summaries automatically
   - **v1.0/v2.0:** Provide a `session_state` summary containing high-level goal, approved specification, implementation plan, and current progress

5. **Follow the workflow** outlined in the prompt for consistent, spec-driven development

## Design Philosophy

This project follows these core principles:

1. **Clarity over hype** — Professional, clear instructions without unnecessary drama
2. **Spec-driven development** — Always plan before implementing
3. **Tool-first approach** — Leverage VS Code tools for all operations
4. **Research-enabled** — Use web research to stay current with dependencies and best practices
5. **Model-specific optimization** — v3.0 tailors prompts to each AI vendor's recommended patterns
6. **Reproducible workflows** — Processes that work in team environments
7. **Rigorous verification** — Test thoroughly before considering work complete

## Contributing

Contributions are welcome. Please open issues or pull requests with clear descriptions of proposed changes.

When contributing:
- Maintain the professional, no-nonsense tone
- Include rationale for prompt changes
- Test changes with actual coding sessions before submitting
- Document which model versions you tested with

## License

These files are provided as-is, with no warranty. Use them however you'd like, responsibly.