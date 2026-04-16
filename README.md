# Agentic Life OS

A token-optimized, zero-friction directory framework designed to turn any large language model (LLM) into a powerful Executive Assistant or Household Command Center.

## What is this?
Instead of forcing AI agents to parse monolithic documents or unstructured folders, **Agentic Life OS** relies on a strict architectural boundary between `context/` (dynamic working memory) and `references/` (encyclopedic stashes). By structuring your data this way, an AI can process your requirements faster, cheaper, and with far greater accuracy.

It comes with two turnkey setups:
1. **VirtualEA**: Your personalized work and professional life assistant.
2. **Stay-At-Home**: A household management command center for logistics, properties, and family life.

## Philosophy: "Strict Alignment"
To keep cognitive overhead low for the agent:
- **`context/`**: High-rotation, active state files (Current Meal Plan, Weekly Priorities, Roster). The AI always reads this.
- **`references/`**: Static records and domain logbooks (Insurance Details, Past Maintenance, Standard Operating Procedures). The AI only reads this when explicitly needed.
- **`.config` (`.VirtualEA` / `.StayAtHome`)**: Hidden rules and system prompts defining boundary behaviors.

## Quickstart Guide

You do not need to build this manually. An AI can build it for you via an onboarding interview.

### Recommended: Claude Code
Use **[Claude Code](https://claude.com/claude-code)** (Claude's native IDE environment) as your setup interface. Claude Code reads `CLAUDE.md` files natively, understands this framework architecture, and has direct file system access for zero-friction scaffolding.

1. **Pick your path**: Decide if you want to build the Virtual EA, the Household Command Center, or both.
2. **Open in Claude Code**: Clone or download this repo and open the folder in Claude Code.
3. **Paste the Setup Prompt**: 
   - Copy the initial prompt from [setup/00_master_init.md](setup/00_master_init.md).
   - Paste into your Claude Code chat window.
4. **Take the Interview**: Claude will ask you questions one by one about your life/work.
5. **Auto-Generate**: Once the interview completes, Claude will create the folder structure and populate it with your data.

### Alternative: Other AI Platforms
If you prefer a different environment (Cursor, GitHub Copilot, Gemini, etc.), the same process works — copy the setup prompt and paste it into your chosen AI sandbox. Claude-based environments (Claude API, Claude Code) offer the best experience due to native `CLAUDE.md` support and prompt caching for repeated reads.
