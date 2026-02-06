---
name: recover
description: Get your work back from the backup pocket (stash) after an undo or restore
allowed-tools: Bash(git stash), Bash(git status)
---

# /kids-cc:recover — Get Work Back from the Backup Pocket

When you use `/undo` or `/restore`, your work gets safely tucked away in a **backup pocket**. This command lets you pull it back out!

## Steps

1. **Check what's in the backup pocket** — Run `git stash list` to see all saved backups
2. **If empty** — Tell them: "🤷 Your backup pocket is empty! Nothing to recover."
3. **Show available backups** — List them in a friendly way with numbers
4. **Ask which one** — If there's only one, confirm they want it. If multiple, let them pick.
5. **Check for conflicts** — Run `git status` to make sure there aren't unsaved changes that might clash
6. **Recover the work** — Run `git stash pop` (for the latest) or `git stash pop stash@{N}` for a specific one
7. **Confirm success** — Show what files came back

## Important Rules

- Use `git stash pop` (not `git stash apply`) so the backup is cleaned up after recovery
- If `git stash pop` fails due to conflicts, explain simply and suggest `/undo` first to get a clean slate
- NEVER silently drop stashes — only remove them via `pop` (successful recovery)
- Show the backup message so users can identify which backup is which

## Example Flow (Single Backup)

> 🔍 Checking your backup pocket...
>
> 📦 I found 1 backup:
> 1. **"kids-cc backup before undo"** — saved 5 minutes ago
>
> **Want me to bring this work back?**

*User confirms*

> ✅ Got it! Your work is back:
> - `index.html` — restored
> - `style.css` — restored
>
> Your backup pocket is now empty. Welcome back, code! 🎉

## Example Flow (Multiple Backups)

> 🔍 Checking your backup pocket...
>
> 📦 I found 3 backups:
> 1. **"kids-cc backup before undo"** — saved 5 minutes ago (newest)
> 2. **"kids-cc backup before restore"** — saved 1 hour ago
> 3. **"kids-cc backup before undo"** — saved yesterday
>
> **Which one do you want to recover?** (Pick a number, or say "newest")

## Example Flow (Conflict)

> ⚠️ Hmm, there's a problem — you have unsaved changes that overlap with the backup.
> Let's save your current work first with `/save`, then try `/recover` again!
