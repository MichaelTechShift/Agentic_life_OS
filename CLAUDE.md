# Agentic Life OS — Framework & Developer Guide

## Collaboration Rule (Read First)
Do not make code changes until you are at least 95% certain about the user's intent
and have a clear path forward. If uncertain, ask for clarification before proceeding.

---

## What This Is
A reusable framework and template library for building LLM-powered Executive Assistants
and Household Command Centers. The framework enforces a strict architectural pattern
(`context/` + `references/` + `.config/`) that keeps AI agents token-efficient and
reduces hallucinations.

## Philosophy: "Strict Alignment"
The framework's core insight: don't make AI agents parse monolithic docs or unstructured
folders. Instead, enforce these boundaries:

- **`context/`** — High-rotation active state (agent reads on every session)
- **`references/`** — Static encyclopedic data (agent reads only on explicit request)
- **`.config/`** — AI rules, system prompts, boundary behaviours (agent loads on startup)

This reduces input tokens by 60–80% compared to unstructured folders, and prevents
"context drift" where stale reference data corrupts agent decisions.

## Products & Use Cases
The framework ships with two turnkey templates:

1. **VirtualEA** — Professional/business assistant. Manages calendar, email, priorities,
   project tracking, team coordination. Stateless per session or persistent per user
   (configurable).

2. **Stay-At-Home** — Household & family assistant. Manages meal planning, shopping,
   schedules, property maintenance, finances, health tracking. Built-in with WhatsApp
   integration and morning/evening handoff automation.

Both can run simultaneously with hard data isolation (no PII crossing boundaries).

## Architecture
```
├── context/              # Active state (high-rotation)
│   ├── priorities.md     # This week's top 3–5 items
│   ├── schedule.md       # Current calendar/roster
│   └── ...
├── references/           # Static data (low-rotation)
│   ├── family/           # Org structure, roles
│   ├── crm/              # Contacts, companies
│   ├── sops/             # Standard operating procedures
│   └── ...
├── .config/              # Agent rules (hidden)
│   ├── system_prompt.md
│   └── rules/
├── decisions/            # ADR-style decision log
├── templates/            # Boilerplate for workflows
└── archives/             # Retired projects/items
```

## Getting Started

### For Users (Non-Developers)
1. Clone or fork this repo
2. Open in [Claude Code](https://claude.com/claude-code) (recommended) or your preferred AI platform
3. Copy the setup prompt from `setup/00_master_init.md`
4. Paste into your AI's chat window
5. Answer the onboarding questions (3–5 minutes)
6. The AI auto-generates your personalized folder structure

### For Developers
The framework is designed for AI-assisted setup but also works as a manual scaffold:
- Adapt the templates in `templates/` to your domain
- Customize the setup prompts in `setup/` for different workflows
- Modify `setup/architecture_rules.md` if you need variations on the core pattern

The framework is LLM-agnostic. It works with Gemini, Claude, GPT, or any model with
file system access and function calling. Claude-native variants (with prompt caching
and `CLAUDE.md` first-class support) are under development.

## Implementation Notes

### Session Persistence
The framework design doesn't mandate session persistence, but it's a best practice:
- Store conversation history per user in SQLite or equivalent
- Load history on every new session
- Prune history to last 20–30 turns to manage token cost

### Prompt Caching
If using Claude, add `cache_control: {"type": "ephemeral"}` to the system prompt.
System prompts are typically 1–2 KB and are sent with every message — caching saves
~90% on repeated token cost.

### Extended Thinking
For complex multi-variable decisions (budget allocation, priority conflicts, long-term
planning), enable extended thinking (`thoughts` mode). This adds latency but improves
reasoning quality on high-stakes decisions.

### Data Isolation
Keep professional data (VirtualEA) and personal data (Stay-At-Home) in separate repos
or separate folder hierarchies. Never share a context window between them. This is a
governance boundary, not a technical one, but it's critical for privacy and correctness.

## Roadmap
- [ ] Claude-native setup (Claude Code first-class support, `CLAUDE.md` templates)
- [ ] Anthropic SDK integration examples
- [ ] Multi-provider adapter examples (Gemini, GPT, Mistral)
- [ ] Mobile integration guide (WhatsApp, Telegram, Signal)
- [ ] Hosting deployment guide (Railway, Heroku, AWS Lambda)

## Contributing
This is a framework and template library. Contributions should focus on:
- New domain templates (healthcare, finance, academic)
- New onboarding interview patterns
- Adapter examples for different LLMs or platforms
- Documentation and examples

## Attribution
Built by TechShift Advisory. Inspired by token-efficient AI agent architecture and
strict information architecture principles.
