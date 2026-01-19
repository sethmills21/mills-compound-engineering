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

## Coding Style

All agents enforce these preferences:
- Explicit over implicit
- No inline conditionals
- Clarity > brevity
- Avoid over-engineering
