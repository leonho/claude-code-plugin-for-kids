# kids-cc — Beginner-Friendly Claude Code Plugin

A [Claude Code](https://docs.anthropic.com/en/docs/claude-code) plugin that makes git safe and approachable for beginners. It replaces intimidating git commands with friendly language, adds safety guardrails to prevent data loss, and encourages new coders along the way.

## Why?

Git is powerful but intimidating — especially for people just learning to code. This plugin:

- **Translates git jargon** into plain language ("commit" becomes "save point", "stash" becomes "backup pocket")
- **Blocks dangerous commands** — no `git push`, `git reset --hard`, `git rebase`, or anything that could permanently destroy work
- **Auto-backs up work** before any destructive operation
- **Encourages you** with friendly messages and emoji feedback
- **Keeps everything local** — no remote operations, no accidental pushes

## Installation

Clone this repo and add the plugin to Claude Code:

```bash
git clone https://github.com/leonho/claude-code-plugin-for-kids.git
claude plugin add ./claude-code-plugin-for-kids/kids-cc
```

Or if you've already cloned it:

```bash
claude plugin add /path/to/claude-code-plugin-for-kids/kids-cc
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

- **Blocked commands:** `git push`, `git reset --hard`, `git clean`, `git rebase`, `git branch -D`, `rm -rf .git`
- **Automatic backups:** Before any undo or restore, work is stashed automatically
- **Confirmation required:** Destructive operations always ask before proceeding
- **Local only:** No changes are ever pushed to remote repositories
- **Tool restrictions:** Each command only has access to the specific git operations it needs

## How It Works

This is a pure prompt-engineering plugin — no dependencies, no build step, no runtime code. It works by:

1. **`CLAUDE.md`** — Sets the friendly personality, git term translations, and safety rules
2. **`commands/`** — Each command is a markdown file with instructions and restricted `allowed-tools`
3. **`skills/kid-friendly-guide/`** — Background glossary loaded automatically into context

### Git Term Translations

| Git Term | Friendly Term |
|----------|------------------|
| commit | save point |
| repository | project folder |
| branch | version |
| stash | backup pocket |
| diff | what changed |
| log | save history |
| conflict | overlap problem |
| revert | undo |

## Project Structure

```
kids-cc/                          # Plugin directory
├── .claude-plugin/
│   └── plugin.json               # Plugin metadata
├── CLAUDE.md                     # Personality & safety rules
├── README.md                     # Plugin docs
├── commands/
│   ├── save.md                   # /kids-cc:save
│   ├── undo.md                   # /kids-cc:undo
│   ├── restore.md                # /kids-cc:restore
│   ├── status.md                 # /kids-cc:status
│   ├── timeline.md               # /kids-cc:timeline
│   ├── help-me.md                # /kids-cc:help-me
│   ├── help.md                   # /kids-cc:help
│   └── recover.md                # /kids-cc:recover
└── skills/
    └── kid-friendly-guide/
        └── SKILL.md              # Auto-loaded glossary & tone guide
```

## Contributing

Contributions welcome! Some ideas:

- Add more commands (e.g., `/kids-cc:branch` for safe branch management)
- Improve explanations and analogies
- Translate to other languages
- Add more safety checks

## License

MIT
