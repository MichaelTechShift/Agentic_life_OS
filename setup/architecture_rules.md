# Agentic Architecture Rules: "Strict Alignment"

When generating files for a user in the Agentic Life OS ecosystem, you MUST follow these file placement rules. This ensures the environment remains token-optimized.

## 1. The `context/` Boundary
**Purpose:** High-rotation, active state working memory.
**What goes here:**
- Current priorities or active short-term goals.
- This week's active meal plan.
- The current, active weekly roster.
- High-level outlines of team members or family members.
**AI Implication:** The agent reads this folder frequently. Keep it light. 

## 2. The `references/` Boundary
**Purpose:** Encyclopedic storage and static logs. 
**What goes here:**
- Domain-specific folders (e.g., `references/family/`, `references/property/`, `references/crm/`).
- Long-term logbooks (Maintenance histories, utility bills, inventory lists).
- SOPs (Standard Operating Procedures) for humans.
- Deep, static documentation.
**AI Implication:** The agent ONLY searches or reads this folder if explicitly asked about a specific domain.

## 3. The `.config` (`.VirtualEA` / `.StayAtHome`) Boundary
**Purpose:** AI Agent Rules and Behavior Constraints.
**What goes here:**
- Communication style rules.
- Protocols for evening sign-offs or morning generation (Agent instructions).
- Tooling endpoints (Webhook configurations).
**AI Implication:** The system prompt should load these automatically or the agent should check these upon starting a new session.

## 4. Work in Progress
- **`projects/`**: Time-boxed efforts with a clear definition of done.
- **`decisions/`**: Decision logs (ADR style) for why a major step was taken.
- **`templates/`**: Boilerplate markdown to trigger daily or weekly workflows.
- **`archives/`**: Where old `projects/` and past `context/` items go to die.
