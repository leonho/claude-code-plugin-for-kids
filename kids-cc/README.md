# kids-cc — Beginner-Friendly Claude Code Plugin

A Claude Code plugin that simplifies git workflows with friendly language, safety guardrails, and encouraging feedback. Perfect for anyone new to git and coding.

## Installation

```bash
claude plugin add /path/to/kids-cc
```

## Commands

| Command | What it does |
|---------|-------------|
| `/kids-cc:save` | Save your work (creates a git save point) |
| `/kids-cc:undo` | Undo your last change (saved or unsaved) |
| `/kids-cc:restore` | Go back to your last save point |
| `/kids-cc:status` | See what's happening in your project |
| `/kids-cc:timeline` | Visual history of all your save points |
| `/kids-cc:help-me` | Explain the last error in simple language |
| `/kids-cc:help` | Show all available commands |
| `/kids-cc:recover` | Get back work from your backup pocket |

## Safety

This plugin is designed with safety as the top priority:

- **Blocked commands:** `git push`, `git reset --hard`, `git clean`, `git rebase`, `git branch -D`
- **Automatic backups:** Before any undo or restore, work is stashed automatically
- **Confirmation required:** Destructive operations always ask before proceeding
- **Local only:** No changes are ever pushed to remote repositories

## How It Works

- `CLAUDE.md` sets the friendly personality, git term translations, and safety rules
- Each command has restricted `allowed-tools` — only the git operations it needs
- The `kid-friendly-guide` skill provides a background glossary loaded automatically
- Git terms are translated: "commit" → "save point", "stash" → "backup pocket", etc.
