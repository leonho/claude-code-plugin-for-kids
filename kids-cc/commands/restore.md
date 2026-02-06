---
name: restore
description: Go back to your latest save point, undoing any unsaved changes
allowed-tools: Bash(git stash), Bash(git checkout), Bash(git status), Bash(git diff)
---

# /kids-cc:restore — Go Back to Your Last Save Point

This undoes all unsaved changes and takes the project back to the last save point. Think of it like loading your last save in a video game.

## Steps

1. **Check if there are unsaved changes** — Run `git status` and `git diff --stat`
2. **If no changes** — Tell them: "✨ You're already at your last save point! Nothing to undo."
3. **Show what will be undone** — List the files that will be affected
4. **Ask for confirmation** — This is important!
   > ⚠️ This will undo your unsaved changes to these files:
   > - `file1.js`
   > - `file2.css`
   >
   > Don't worry — I'll put your current work in a **backup pocket** first, so you can get it back if you change your mind!
   >
   > **Do you want to go back to your last save point?**
5. **Create a backup** — Run `git stash push -m "kids-cc backup before restore [timestamp]"`
6. **Restore** — Run `git checkout -- .` to restore all files to their last committed state
7. **Confirm success**

## Important Rules

- **ALWAYS stash before restoring** — never skip the backup
- **ALWAYS ask for confirmation** — show them exactly what will change
- **NEVER use `git reset --hard`** — use `git checkout -- .` instead (safer)
- **NEVER use `git clean -f`** — if there are new untracked files, the stash will handle them
- Tell them how to get their backup back: "If you change your mind, just let me know and I can grab your work from the backup pocket!"

## Example Flow

> 🔍 Let me check what's changed since your last save point...
>
> You have unsaved changes in 2 files:
> - `index.html` — 5 lines changed
> - `style.css` — 2 lines changed
>
> ⚠️ **Going back to your last save point will undo these changes.**
> I'll put your current work in a backup pocket first, just in case!
>
> **Ready to go back?**

*User confirms*

> 🔒 Backed up your work to the backup pocket!
> ⏪ Going back to your last save point...
> ✅ Done! Your project is back to how it was at your last save. Clean slate! ✨
