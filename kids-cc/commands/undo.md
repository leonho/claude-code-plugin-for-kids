---
name: undo
description: Undo your last change — works for both saved and unsaved changes
allowed-tools: Bash(git stash), Bash(git checkout), Bash(git revert), Bash(git status), Bash(git diff), Bash(git log)
---

# /kids-cc:undo — Undo Your Last Change

This command helps undo the last thing that happened. It handles two cases:

## Case 1: Unsaved Changes Exist

If there are uncommitted changes, undo means "throw away my unsaved edits."

### Steps
1. Run `git status` and `git diff --stat` to see what's changed
2. Show the user what will be undone
3. **Ask for confirmation**
4. Run `git stash push -m "kids-cc backup before undo [timestamp]"` — ALWAYS backup first
5. Run `git checkout -- .` to discard changes
6. Confirm success and remind them about the backup pocket

## Case 2: No Unsaved Changes (Undo Last Save Point)

If the working tree is clean, undo means "reverse my last save point."

### Steps
1. Run `git log --oneline -5` to show recent save points
2. Show the user what the last save point was:
   > Your last save point was: "added the login page"
   > This will create a NEW save point that reverses those changes.
3. **Ask for confirmation**
4. Run `git stash push -m "kids-cc backup before undo [timestamp]"` (in case there's anything)
5. Run `git revert HEAD --no-edit` to create a new commit that undoes the last one
6. Confirm success

## Important Rules

- **ALWAYS create a backup (stash) before ANY undo operation**
- **ALWAYS ask for confirmation** — show exactly what will be undone
- **NEVER use `git reset --hard`** — use `git revert` for commits, `git checkout -- .` for uncommitted changes
- **NEVER undo more than one save point at a time** — if they want to go further back, suggest doing it step by step
- If `git revert` causes a conflict, explain it simply and help them through it
- Remind them: "Your work is safe in the backup pocket if you change your mind!"

## Example Flow (Case 1 — Unsaved changes)

> 🔍 Checking what you want to undo...
>
> You have unsaved changes in:
> - `app.js` — 10 lines changed
>
> 🗑️ **Do you want to undo these unsaved changes?**
> I'll back them up first so you can get them back if needed!

*User confirms*

> 🔒 Backed up! ⏪ Undoing...
> ✅ Changes undone! Your files are back to how they were at your last save point.

## Example Flow (Case 2 — Clean tree, undo last commit)

> 🔍 No unsaved changes found. Let me look at your last save point...
>
> Your last save point was: **"added the login page"**
> Undoing this will reverse those changes (but it creates a new save point so you can always undo the undo!).
>
> **Do you want to undo this save point?**

*User confirms*

> ⏪ Undoing your last save point...
> ✅ Done! The changes from "added the login page" have been reversed.
> You now have a new save point: "Revert: added the login page" 🔄
