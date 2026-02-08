# {{AGENT_NAME}} Brain Template

A reusable skeleton for new specialist agent brains in DeFiZoo.

## What This Is

This template provides the standard workspace structure for DeFiZoo specialist agents:
- `AGENTS.md` — Role, responsibilities, and workflow
- `IDENTITY.md` — Name, creature type, vibe, emoji
- `SOUL.md` — Personality, principles, safety rules
- `TOOLS.md` — GitHub setup, model providers, Discord channels
- `USER.md` — Human operator info
- `HEARTBEAT.md` — Comments only, no active heartbeat
- `MEMORY.md` — Agent learnings accumulate here

## How It Connects

This brain works as an isolated session within the DeFiZoo orchestrator:
- Zoo Keeper routes questions to the appropriate specialist
- Each brain keeps domain knowledge self-contained
- All knowledge evolution happens via git commits and PRs

## How to Use This Template

### Step 1: Create the Brain Repo

```bash
# Create a new repo (private or public) under DeFiZooKeeper
gh repo create DeFiZooKeeper/{{AGENT_ID}}-brain --public --description "{{AGENT_NAME}} brain — workspace for {{DOMAIN}}"

# Or create manually at https://github.com/new
```

### Step 2: Clone and Replace Placeholders

```bash
git clone https://github.com/DeFiZooKeeper/{{AGENT_ID}}-brain.git
cd {{AGENT_ID}}-brain

# Replace all {{PLACEHOLDER}} tokens:
# - {{AGENT_ID}} → e.g., "frontend", "solidity", "ops"
# - {{AGENT_NAME}} → e.g., "Frontend Elephant", "Solidity Monkey"
# - {{EMOJI}} → e.g., "🐘", "🐒"
# - {{DOMAIN}} → e.g., "frontend", "smart contracts", "devops"
```

### Step 3: Update Orchestrator Registration

Edit these files in the orchestrator repo (`workspace/`):
- `AGENTS.md` — Add agent row to roster table
- `setup-brains.sh` — Add brain to `BRAIN_REPOS` and loops
- `state/openclaw.json` — Add agent to `agents.list`, `tools.agentToAgent.allow`, and `bindings`

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
| `AGENTS.md` | Role definition and workflow |
| `IDENTITY.md` | Agent identity fields |
| `SOUL.md` | Personality and principles |
| `TOOLS.md` | Tools and access setup |
| `USER.md` | Human operator info |
| `HEARTBEAT.md` | Empty (comments only) |
| `MEMORY.md` | Agent learnings accumulate here |

## Next Steps After Template Setup

1. Run `git add -A && git commit -m "feat: init brain from template"`  
2. Push to the newly created repo  
3. Update orchestrator registration files  
4. Test the agent's ability to clone and work in its brain repo
