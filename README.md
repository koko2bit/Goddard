# Goddard

> Pre-alpha — not yet released. Backwards compatibility is not guaranteed.

## What Is It

Goddard is a local AI developer platform that connects your repositories, GitHub, and autonomous AI agents in one place. It runs a background daemon on your machine that manages AI coding sessions, handles pull request events from GitHub in real time, and orchestrates multi-agent work across your codebase.

The platform ships as three surfaces that all talk to the same daemon:

- **Desktop app** — an IDE-like workspace to monitor agent sessions, review pull requests, and steer ongoing automation without switching tools.
- **SDK (`@goddard-ai/sdk`)** — a TypeScript library for programmatically controlling the daemon from any host (Node, browser, custom tooling).
- **CLI (`goddard-workforce`)** — a thin operator tool for initializing and inspecting repository-scoped multi-agent runs from the terminal.

## Why It Was Built

Developer execution is fragmented: code lives in an IDE, pull requests live in GitHub, AI agents run in separate chat tools, and automation scripts are ad hoc. Goddard was built to close two gaps:

1. **Workspace gap** — bring GitHub operations and AI steering into a single local surface so developers don't context-switch between tools.
2. **Autonomous gap** — give AI agents a principled, daemon-managed runtime for long-running and feedback-triggered work instead of fire-and-forget scripts.

## Tech Stack

| Area | Technology |
|------|-----------|
| Language | TypeScript 6 |
| Runtime | Bun 1.3.11 |
| Monorepo orchestration | Turborepo |
| Desktop shell | Electrobun |
| UI framework | Preact (with React compat) |
| UI components | Ark UI |
| Styling | Panda CSS |
| Backend | Cloudflare Workers |
| Schema validation | Zod 4 |
| Linting | oxlint |
| Formatting | Prettier |


## Getting Started

Requires [Bun](https://bun.sh) >= 1.3.11.

```sh
bun install
bun run dev
```

Other useful commands:

| Command | What it does |
|---------|-------------|
| `bun run build` | Build all packages |
| `bun run check` | Typecheck + lint + test in one pass |
| `bun run test` | Run all workspace tests |
| `bun run typecheck` | Type checking only |
| `bun run lint` | Lint with oxlint |
| `bun run fmt` | Format with Prettier |
| `bun run goddard:daemon` | Start the daemon in development mode |
| `bun run goddard:workforce` | Start the workforce runtime in development mode |

> Use `bun run test` from the repo root, not `bun test` — the latter bypasses monorepo test orchestration.
