# Changelog

All notable changes to this skill distribution are documented here.

This repository is auto-mirrored from [agentmark-ai/agentmark](https://github.com/agentmark-ai/agentmark) — see that repo's history for per-commit detail on the skill content itself. The entries below summarize externally-visible releases.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/). This project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html), with the caveat that the skill's behavior depends on the underlying model — a "no breaking changes" release can still drift if Anthropic releases a model that interprets the same description differently.

## [0.1.0] - 2026-05-20

### Added

- Initial public release of the AgentMark agent skill.
- `skills/agentmark/SKILL.md` — entry point, 903-char description with TRIGGER/SKIP clauses mirroring the [`anthropics/skills/claude-api`](https://github.com/anthropics/skills/blob/main/skills/claude-api/SKILL.md) reference.
- Five workflow files: `creating-prompts.md`, `building-datasets.md`, `running-experiments.md`, `using-evals.md`, `deploying.md`.
- Four auto-generated reference files (regenerated on every CLI release from upstream sources):
  - `reference/cli-commands.md` — from `cli-src/index.ts`
  - `reference/frontmatter-schema.md` — from `prompt-core/src/schemas.ts` (Zod schemas)
  - `reference/api-commands.md` — from `cli-src/server/openapi-spec.json`
  - `reference/models.md` — from `@agentmark-ai/model-registry`
- Eval scenarios at `skills/agentmark/evals/scenarios.json` (3 positive + 3 negative) with structured machine-checkable `checks`.
- Cross-tool guidance at root `AGENTS.md` for OpenAI Codex / Cursor / Copilot / Aider / Zed / goose consumers.

### Provenance

Source commit: agentmark-ai/agentmark@(seeded from initial publish).

[0.1.0]: https://github.com/agentmark-ai/skills/releases/tag/v0.1.0
