# {{AGENT_NAME}} Brain Template

A reusable skeleton for specialist agent brains in DeFiZoo — **optimized for company-wide Discord** with many people and busy channels.

## What This Is

This template provides the standard workspace structure for DeFiZoo specialist agents:
- `AGENTS.md` — Operations manual, rules, workflow (group chat, many people)
- `BOOTSTRAP.md` — First-run ritual: confirm identity, replace placeholders, then delete
- `IDENTITY.md` — Name, creature, vibe, emoji
- `SOUL.md` — Personality, values, boundaries (team-serving)
- `TOOLS.md` — Discord channels, repos, agent roster
- `USER.md` — Company context, humans vs AI colleagues
- `HEARTBEAT.md` — Periodic task checklist (@mentions, shared inbox)
- `MEMORY.md` — Company/team knowledge (decisions, conventions)

## How It Connects

This brain works as an isolated session within the DeFiZoo orchestrator:
- Zoo Keeper routes questions to the appropriate specialist
- Agents serve the whole team in Discord — many people, many channels
- Each brain keeps domain knowledge self-contained
- All knowledge evolution happens via git commits and PRs

## How to Use This Template

### Step 1: Create the Brain Repo

```bash
# Create a new repo (private or public) under DeFiZooKeeper
gh repo create DeFiZooKeeper/{{AGENT_ID}}-brain --public --description "{{AGENT_NAME}} brain — workspace for {{DOMAIN}}"

# Or create manually at https://github.com/new
```

### Step 2: Clone Template and Run Bootstrap

```bash
git clone https://github.com/DeFiZooKeeper/template-brain.git
cd template-brain
# Rename to your agent's brain repo, or copy contents into a new repo

# Option A: Run the agent — BOOTSTRAP.md guides the first-run ritual.
# The agent will ask "Which specialist am I?" and replace placeholders.

# Option B: Replace placeholders manually before first run:
# - {{AGENT_ID}} → e.g., "frontend", "solidity", "api"
# - {{AGENT_NAME}} → e.g., "Frontend Falcon", "Solidity Shark"
# - {{EMOJI}} → e.g., "🦅", "🦈"
# - {{DOMAIN}} → e.g., "frontend", "smart contracts"
```

### Step 3: Update Orchestrator Registration

Edit these files in the orchestrator repo (`workspace/`):
- `AGENTS.md` — Add agent row to roster table
- `setup-brains.sh` — Add brain to `BRAIN_REPOS` and loops
- `state/openclaw.json` — Add agent to `agents.list`, `tools.agentToAgent.allow`, and `bindings`

**Agent-to-agent:** Specialists query each other (and HR) via `sessions_send`. Enable `tools.agentToAgent.enabled: true` and add all agents to `tools.agentToAgent.allow`. Each agent's TOOLS.md has the agent roster — keep it in sync across repos.

### Step 4: Wire in Docker (if applicable)

Add the brain to `docker-compose.yml` services or orchestration config if using containerized deployments.

### Step 5: Start Working

```bash
# The agent now has a dedicated brain workspace
# All domain knowledge lives in commits and MEMORY.md
```

## Template Contents

| File | Purpose |
|------|---------|
| `AGENTS.md` | Operations manual, rules, workflow (group chat) |
| `BOOTSTRAP.md` | First-run ritual — delete after setup |
| `SOUL.md` | Personality, values, boundaries (team-serving) |
| `IDENTITY.md` | Name, creature, vibe, emoji |
| `TOOLS.md` | Discord channels, repos, agent roster |
| `USER.md` | Company context, humans vs AI colleagues |
| `HEARTBEAT.md` | Periodic task checklist (@mentions, inbox) |
| `MEMORY.md` | Company/team knowledge |

## Next Steps After Template Setup

1. Run `git add -A && git commit -m "feat: init brain from template"`  
2. Push to the newly created repo  
3. Update orchestrator registration files  
4. Test the agent's ability to clone and work in its brain repo

## Git Safety Rules (CRITICAL)

- **ONLY update your own brain repo**: You MUST NOT clone or modify any other repository.
- **NEVER commit to main**: Always work on branch `agent/{{AGENT_ID}}`, push, and open a PR — human merges.
- **Per-commit git name**: EVERY time you make a commit/push, you MUST run:
  ```bash
  git config user.name "{{AGENT_NAME}}"
  git config user.email "{{AGENT_ID}}@defizoo.ai"
  ```
- **Verify repo URL before cloning**: Always ensure the remote is your own brain repo (`DeFiZooKeeper/{{AGENT_ID}}-brain`).
