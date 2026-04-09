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

1. **Pick your path**: Decide if you want to build the Virtual EA, the Household Command Center, or both.
2. **Copy the Prompt**: 
   - Open [setup/00_master_init.md](setup/00_master_init.md) and copy the initial prompt.
   - Paste it into your preferred Agentic AI Sandbox (e.g., Cursor, GitHub Copilot Workspace, Gemini, Claude Computer Use).
3. **Take the Interview**: The AI will ask you questions one by one about your life/work.
4. **Auto-Generate**: Once the interview completes, the AI will automatically create the folder structure found in `templates/` and populate it with your data.
