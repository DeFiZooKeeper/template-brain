# TOOLS.md - DeFiZoo {{DOMAIN}} Notes

Skills define *how* tools work. This file is for *your* specifics — the stuff unique to your team's setup.

## What Goes Here

Things like:

* Discord channels and their purpose
* Available {{DOMAIN}} tools, repos, APIs, environments
* SSH hosts, credentials (placeholders only)
* Team conventions and workflows
* Anything environment-specific

## Agent Roster (Cross-Agent Queries)

When you need info outside your {{DOMAIN}}, ask the right agent via `sessions_send`. Session key format: `agent:<id>:main`.

| Agent | Name | Ask when you need... |
|-------|------|----------------------|
| `orchestrator` | head agent | routing, cross-domain coordination, escalation, creating new agents, "who owns this?" |
| `hr` | HR Horse 🐴 | team structure, who does what, policies, org |
| `marketing` | Marketing Monkey 🐵 | campaigns, messaging, content, positioning |
| `frontend` | Frontend Falcon 🦅 | UI, React, client-side, integration points |
| `api` | API Alligator 🐊 | APIs, services, data models, endpoints |
| `solidity` | Solidity Shark 🦈 | contracts, deployments, chain, ABIs |

**Add/remove rows** as your org's agents change. Keep this in sync across all agent repos — it's shared org structure.

**Config required:** In `openclaw.json`, set `tools.agentToAgent.enabled: true` and add all agents to `tools.agentToAgent.allow` so they can query each other.

## Discord Channels

| Channel | Purpose |
|---------|---------|
| #{{DOMAIN}} | Primary {{DOMAIN}} channel — your main home |
| _(add others)_ | |

## Examples (adapt for {{DOMAIN}})

```markdown
### Repositories
- main-contracts → Smart contracts in `/contracts/`
- frontend-app → Next.js frontend at `/frontend/`

### Environments  
- dev → Local development
- staging → `https://staging.defizoo.com`
- prod → `https://app.defizoo.com`

### API Keys (placeholders only — never real values)
- mainnet → `ALCHEMY_API_KEY_MAINNET="REDACTED"`
```

## Why Separate?

Skills are shared. Your team's setup is yours. Keep them apart so you can update skills without losing notes, and share without leaking infrastructure.

***

Add whatever helps you serve the team. This is your cheat sheet.