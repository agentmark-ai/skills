# AgentMark agent skills

Claude Code / agent skill that teaches AI agents how to use [AgentMark](https://agentmark.co) — CLI commands, prompt authoring, datasets, experiments, evals, and git-based deploys.

## Install

Pick whichever fits your tooling:

**Universal (`npx skills`, cross-tool — Claude Code, Codex, Cursor, GitHub Copilot, Amp, Antigravity, +others):**

```bash
npx skills add agentmark-ai/skills
```

Files land in `./.agents/skills/agentmark/` with symlinks into per-tool paths automatically.

**Native Claude Code plugin marketplace:**

```bash
claude
> /plugin marketplace add agentmark-ai/skills
> /plugin install agentmark
```

This uses Claude Code's built-in plugin system (`.claude-plugin/marketplace.json` in this repo declares the marketplace).

**Mintlify well-known discovery (for any AgentMark docs URL):**

```bash
npx skills add docs.agentmark.co
```

Once installed, Claude Code (or any agentskills.io-compatible tool) auto-discovers the skill at session start and invokes it when AgentMark context appears (`.prompt.mdx` files, `agentmark.json`, `@agentmark-ai/*` imports, or explicit mentions of AgentMark / CLI commands).

## What's in this repo

```
skills/agentmark/
├── SKILL.md                          # entry point — read by Claude on auto-invoke
├── workflows/                        # one file per common task
│   ├── creating-prompts.md
│   ├── building-datasets.md
│   ├── running-experiments.md
│   ├── using-evals.md
│   └── deploying.md
├── reference/                        # auto-generated, do not hand-edit
│   ├── cli-commands.md               # ← from cli-src/index.ts
│   ├── frontmatter-schema.md         # ← from prompt-core schemas.ts
│   ├── api-commands.md               # ← from openapi-spec.json
│   └── models.md                     # ← from model-registry
└── evals/scenarios.json              # eval scenarios for skill validation
```

## How it stays current

The skill is **a thin pointer that delegates to live docs**, not a static reference. It teaches agents to:

1. Run `npx agentmark <cmd> --help` for canonical CLI surface
2. Fetch `https://docs.agentmark.co/llms.txt` for doc navigation
3. WebFetch specific `.md` pages from `docs.agentmark.co` for content

The four `reference/*.md` files are auto-generated from the canonical sources in [agentmark-ai/agentmark](https://github.com/agentmark-ai/agentmark) on every release, so encoded facts can't drift.

## Do not edit directly

**This repo is auto-generated from [agentmark-ai/agentmark](https://github.com/agentmark-ai/agentmark).**

Changes belong in `skills/agentmark/` of the source repo. On every CLI release, a GitHub Action mirrors the source `skills/` directory here. Direct commits to this repo will be overwritten on the next sync.

For substantive proposals, open an issue or PR against [agentmark-ai/agentmark](https://github.com/agentmark-ai/agentmark).

## License

Same as AgentMark — AGPL-3.0-or-later.
