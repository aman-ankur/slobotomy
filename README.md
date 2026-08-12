# slobotomy

Surgical removal of AI slop from your writing.

A skill for coding agents (Claude Code, Codex, Gemini CLI, Copilot CLI) that edits drafts into sharper, more human prose — or flags AI-slop patterns without rewriting. It preserves the writer's voice instead of smoothing it into generic polish.

Inspired by [petergyang/no-ai-slop](https://github.com/petergyang/no-ai-slop) and Hardik Pandya's `stop-slop`. Extended with a personal banned-word list, business-jargon swaps, and a portability test.

## What it does

Three modes:

- **Edit** — Paste a draft. Get back a tighter version plus a bulleted list of what changed.
- **Detect** — Ask "is this slop?" and get named patterns with quoted lines and one-line fixes. No rewrite, no guessing AI authorship.
- **Generate** — Ask for maximum slop about a topic. Satire that makes the patterns visible.

## Patterns it catches

Binary contrasts, throat-clearing openers, faux-insight setups, colon reveals, dramatic fragments, superficial `-ing` analysis, importance puffery, weasel attribution, fake-strong verbs, synonym cycling, fake-profound kickers, summary-recap endings, emoji headings and decorative bold, em-dash rhythm crutches, hedge stacking, passive voice hiding agency, exclamation inflation, and more. Plus a banned-word list and business-jargon swaps.

## Install

The skill is three markdown files. Any coding agent that supports the [Agent Skills spec](https://agentskills.io/specification) will pick it up from the right directory.

### Claude Code

Personal (all projects):
```bash
git clone https://github.com/aman-ankur/slobotomy.git ~/.claude/skills/slobotomy
```

Project-scoped:
```bash
git clone https://github.com/aman-ankur/slobotomy.git .claude/skills/slobotomy
```

### Codex CLI, Copilot CLI, Gemini CLI

These runtimes read from `~/.agents/skills/` (the cross-runtime alias):
```bash
git clone https://github.com/aman-ankur/slobotomy.git ~/.agents/skills/slobotomy
```

### ChatGPT / Codex (managed)

Paste into the chat:
```
Install the /slobotomy skill globally from https://github.com/aman-ankur/slobotomy
```

### One-liner via npx

If you have the [skills CLI](https://www.npmjs.com/package/skills):
```bash
npx skills add aman-ankur/slobotomy --skill slobotomy --global --yes
```

### Manual

Copy `SKILL.md` and `eval.md` into any directory your agent scans for skills.

## Use

```
Edit this: <paste draft>
```

```
Slobotomize this: <paste draft>
```

```
Is this slop? <paste draft>
```

```
Draft an AI slop post about founder mode
```

## Files

- `SKILL.md` — rules and workflow (loaded by the agent)
- `eval.md` — self-check the skill runs before returning an edit
- `README.md` — this file

## Credit

Original patterns and structure from Peter Yang's [no-ai-slop](https://github.com/petergyang/no-ai-slop). Additional patterns from Hardik Pandya's `stop-slop`.

## License

MIT.
