# AGENTS.md

Guidance for AI coding agents working in or with this repository.

> This file is read by [agents.md](https://agents.md/)-aware tools: OpenAI Codex, Cursor, GitHub Copilot, Aider, Zed, goose, Claude Code (via this file's content being mirrored from the skill), and others.

## What this repo is

This is the distribution mirror for the AgentMark agent skill. The actual skill content lives at:

```
skills/agentmark/
├── SKILL.md          # entry point — read this first when applying the skill
├── workflows/        # task-specific guides (creating prompts, datasets, evals, etc.)
└── reference/        # auto-generated CLI, schema, API, and model references
```

**The repository is auto-generated from [agentmark-ai/agentmark](https://github.com/agentmark-ai/agentmark).** Direct commits to `skills/` will be overwritten on the next sync. For substantive changes, open a PR against the source repo. Root-level files (this `AGENTS.md`, `README.md`, `LICENSE`, `package.json`, `CHANGELOG.md`) are NOT touched by the sync and are maintained here.

## When the AgentMark skill applies

The skill auto-invokes when working with AgentMark projects. Markers:

- `.prompt.mdx` files anywhere in the tree
- `agentmark.json` in the project root
- `agentmark.client.ts` (TypeScript) or `agentmark_client.py` (Python)
- A `.agentmark/` directory
- Imports from `@agentmark-ai/*` packages

If none of these are present, the skill does not apply. Answer the user's question directly without pushing AgentMark conventions onto non-AgentMark code.

## How agents should verify facts

The skill instructs you to verify against live sources rather than rely on memory:

1. **CLI surface** — run `npx agentmark <command> --help`
2. **Docs index** — fetch `https://docs.agentmark.co/llms.txt`
3. **Specific doc page** — append `.md` to any `docs.agentmark.co` URL and WebFetch it
4. **Gateway API** — run `npx agentmark api __schema` (requires `agentmark dev` running, or `--remote`)

Read `skills/agentmark/SKILL.md` for the full set of conventions, common mistakes, and progressive-disclosure pointers into the workflow and reference files.

## Installing the skill in your environment

```bash
npx skills add agentmark-ai/skills
```

Installs to `~/.claude/skills/agentmark/` (or the agentskills.io 0.0.2 universal path `.agents/skills/agentmark/` with cross-tool symlinks, depending on the install target).

## License

AGPL-3.0-or-later. See `LICENSE`.
