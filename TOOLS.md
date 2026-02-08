# TOOLS.md — {{AGENT_NAME}} Notes

## GitHub Access

**Account:** [DeFiZooKeeper](https://github.com/DeFiZooKeeper) (personal account)

Tools available:
- `git` — configured as "Zoo Keeper <zookeeper@defizoo.ai>"

### Brain Repo

| Agent | Repo | Purpose |
|-------|------|---------|
| {{AGENT_NAME}} | `DeFiZooKeeper/{{AGENT_ID}}-brain` | {{DOMAIN}} workspace |

### Other Repos

_(Add project repos as you work with them)_

### Quick Reference

```bash
# Clone your brain repo
git clone https://github.com/DeFiZooKeeper/{{AGENT_ID}}-brain.git

# Create a branch and PR
cd {{AGENT_ID}}-brain
git checkout -b feat/my-change
# ... make changes ...
git add -A && git commit -m "feat: description"
git push -u origin HEAD
gh pr create --title "Title" --body "Description"
```

## Model Providers

| Provider | Model | Role |
|----------|-------|------|
| OpenRouter | `qwen/qwen3-coder-next` | Primary |

## Discord Channels

| Channel | Agent | Notes |
|---------|-------|-------|
| `#{{DOMAIN}}` | {{AGENT_NAME}} | No mention required |
