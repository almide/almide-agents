# almide-agents

[日本語](./README.ja.md)

A drop-in reference package that teaches any coding agent — Claude Code, Codex, or otherwise — how to write [Almide](https://github.com/almide/almide) correctly on the first try.

Almide is a statically-typed language designed specifically for LLM code generation. The compiler's own diagnostics are written to be read by an agent and fixed automatically. This package is the syntax/stdlib reference that closes the loop: give it to your agent before it writes a single line.

## Getting started with Almide itself

No installation required — [try it in the browser](https://almide.github.io/playground/).

To install locally:

```bash
# macOS / Linux
curl -fsSL https://raw.githubusercontent.com/almide/almide/main/tools/install.sh | sh
```

```powershell
# Windows
irm https://raw.githubusercontent.com/almide/almide/main/tools/install.ps1 | iex
```

Then set up this package (below) so your agent knows the syntax, and ask it to write something:

```bash
almide run app.almd
```

## Contents

- **`AGENTS.md`** — the reference, in the emerging cross-tool [AGENTS.md](https://agents.md/) convention (Codex and other tools read this automatically from a project root).
- **`claude-skill/almide/SKILL.md`** — the same reference, packaged as a [Claude Code skill](https://docs.claude.com/en/docs/claude-code/skills).

## Usage

### Claude Code

Copy (or symlink) the skill directory into your user-level skills folder:

```bash
git clone https://github.com/almide/almide-agents.git /tmp/almide-agents
cp -r /tmp/almide-agents/claude-skill/almide ~/.claude/skills/almide
```

Claude Code will pick it up automatically whenever a task involves Almide.

### Codex (or any AGENTS.md-reading tool)

Copy `AGENTS.md` into the root of the project where you want to write Almide:

```bash
curl -o AGENTS.md https://raw.githubusercontent.com/almide/almide-agents/main/AGENTS.md
```

If your project already has an `AGENTS.md`, append this one's contents instead of overwriting it.

### Anything else

`AGENTS.md` is plain Markdown with no tool-specific syntax. Paste it into a system prompt, a project-instructions field, or a chat message — any model will be able to use it.

## Why this exists

Almide's own [CHEATSHEET.md](https://github.com/almide/almide/blob/develop/docs/CHEATSHEET.md) has always been written for AI code generation. This repo just makes it installable, instead of something you have to remember to paste in by hand.

## Keeping this in sync

This reference mirrors `docs/CHEATSHEET.md` in the main [almide/almide](https://github.com/almide/almide) repo. If the language changes, that's the source of truth — PRs updating this repo to match are welcome.
