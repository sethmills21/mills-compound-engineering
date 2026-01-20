# mills-compound-engineering

Personal Claude Code plugin for Node.js/Express, Swift/iOS, and Vue/Nuxt development.

## Stack-Specific Agents

| Agent | Purpose |
|-------|---------|
| `node-express-reviewer` | Node.js/Express/MongoDB patterns |
| `swift-ios-reviewer` | Swift 6, SwiftUI, UIKit patterns |
| `vue-nuxt-reviewer` | Vue 2, Nuxt 2, Composition API |

## Universal Agents

| Agent | Purpose |
|-------|---------|
| `security-sentinel` | Security audits, OWASP compliance |
| `performance-oracle` | Performance analysis |
| `architecture-strategist` | System design review |
| `code-simplicity-reviewer` | YAGNI, simplicity checks |
| `git-history-analyzer` | Git archaeology |
| `best-practices-researcher` | External research |
| `bug-reproduction-validator` | Bug verification |
| `pr-comment-resolver` | PR comment handling |

## Installation

```bash
claude plugin add https://github.com/sethmills21/mills-compound-engineering
```

## Usage

Agents are auto-invoked when appropriate, or manually:

```bash
claude agent node-express-reviewer "review this Express middleware"
claude agent swift-ios-reviewer "check this SwiftUI view"
```

## Commands & Skills

| Type | Name | Invocation |
|------|------|------------|
| Command | changelog | `/mills-compound-engineering:changelog` |
| Skill | git-worktree | `/mills-compound-engineering:git-worktree` |

## Coding Style

All agents enforce these preferences:
- Explicit over implicit
- No inline conditionals
- Clarity > brevity
- Avoid over-engineering

## Updating the Plugin

When you make changes to the plugin:

```bash
# 1. Make edits in the plugin directory
cd ~/code/mills-compound-engineering/plugins/mills-compound-engineering

# 2. Commit and push
cd ~/code/mills-compound-engineering
git add -A && git commit -m "your message" && git push

# 3. Update the installed plugin
claude plugin update mills-compound-engineering@mills-compound-engineering

# 4. Restart Claude Code for changes to take effect
```

## Plugin Management

| Task | Command |
|------|---------|
| Check status | `claude plugin list` |
| Update | `claude plugin update mills-compound-engineering@mills-compound-engineering` |
| Disable | `claude plugin disable mills-compound-engineering@mills-compound-engineering` |
| Enable | `claude plugin enable mills-compound-engineering@mills-compound-engineering` |

## File Structure

```
mills-compound-engineering/
├── .claude-plugin/marketplace.json
└── plugins/mills-compound-engineering/
    ├── .claude-plugin/plugin.json
    ├── agents/
    │   ├── review/          # Code review agents
    │   ├── research/        # Research agents
    │   └── workflow/        # Workflow agents
    ├── commands/            # Slash commands
    └── skills/              # Interactive skills
```
