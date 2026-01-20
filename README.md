# mills-compound-engineering

A lean, personalized fork of [Every's compound-engineering plugin](https://github.com/EveryInc/compound-engineering-plugin) for Claude Code.

## Why This Fork?

The original [compound-engineering plugin](https://github.com/EveryInc/compound-engineering-plugin) is excellent (read their [blog post](https://every.to/chain-of-thought/compound-engineering-how-every-codes-with-agents) explaining the philosophy), but it includes 24+ agents and many features I don't use. Loading all those agent descriptions into context costs ~15-16k tokens per session.

This fork is:
- **Lean**: 11 agents vs 24+ (saves ~10k tokens/session)
- **Stack-specific**: Custom agents for my exact stack (Node/Express, Swift/iOS, Vue/Nuxt)
- **Personalized**: Enforces my coding style preferences across all agents

## My Stack

- **Backend**: Node.js, Express, MongoDB, Redis
- **iOS**: Swift 6, SwiftUI, UIKit
- **Web**: Vue 2, Nuxt 2

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

## Creating Your Own Fork

If you want to create a lean, personalized plugin for your stack:

1. **Start from Every's plugin** or this repo as a template
2. **Delete agents you don't use** - be ruthless, each agent costs tokens
3. **Create stack-specific agents** - copy an existing agent and customize for your framework
4. **Enforce your style** - add your coding preferences to each agent's instructions
5. **Rename everything** - update `plugin.json`, folder names, and `marketplace.json`

Key files to customize:
- `plugins/*/agents/**/*.md` - Agent instructions
- `plugins/*/.claude-plugin/plugin.json` - Plugin identity
- `.claude-plugin/marketplace.json` - Registry metadata

## Complementary Plugins

These plugins work great alongside this one:

| Plugin | Purpose | Install |
|--------|---------|---------|
| [Swift Concurrency Agent Skill](https://github.com/AvdLee/Swift-Concurrency-Agent-Skill) | Deep Swift 6 concurrency expertise from [@AvdLee](https://twitter.com/twannl) | `claude plugin marketplace add AvdLee/Swift-Concurrency-Agent-Skill && claude plugin install swift-concurrency@swift-concurrency-agent-skill` |

The `swift-ios-reviewer` in this plugin handles general Swift/iOS patterns and code style, while AvdLee's skill provides deep expertise on async/await, actors, Sendable, and Swift 6 migration.

## Credits

- [Every's compound-engineering plugin](https://github.com/EveryInc/compound-engineering-plugin) - The original plugin this is forked from
- [Compound Engineering blog post](https://every.to/chain-of-thought/compound-engineering-how-every-codes-with-agents) - The philosophy behind it
- [AvdLee's Swift Concurrency Agent Skill](https://github.com/AvdLee/Swift-Concurrency-Agent-Skill) - Swift concurrency inspiration
- [Swift Concurrency Course](https://www.swiftconcurrencycourse.com/) - Antoine van der Lee's comprehensive course
