---
name: status
description: See what's happening in your project — what changed, what's saved, and your recent save history
allowed-tools: Bash(git status), Bash(git log), Bash(git diff)
---

# /kids-cc:status — Project Status Check

Run these three git commands and present the results in beginner-friendly language:

1. `git status` — Show which files have been changed, which are new, and which are ready to save
2. `git log --oneline -10` — Show the last 10 save points
3. `git diff --stat` — Show a summary of what changed

## How to Present Results

### Changed Files
- List each changed file with a simple description of its status:
  - 📝 **Modified** → "You edited this file"
  - 🆕 **Untracked** → "This is a brand new file"
  - 🗑️ **Deleted** → "This file was removed"
  - ✅ **Staged** → "This file is ready to save"

### Save History
- Show recent save points as a simple numbered list
- Use the save point message, not the hash

### What Changed
- Show a brief summary: "You changed X files, adding Y lines and removing Z lines"

### Example Output Format

```
📊 **Project Status**

📝 **Files you've been working on:**
- 📝 `src/app.js` — edited
- 🆕 `src/helper.js` — brand new file

💾 **Your last few save points:**
1. Added the login page
2. Fixed the color of the button
3. Started the project

📈 **Quick summary:** You changed 2 files since your last save point.
```

Keep it simple, friendly, and encouraging. If everything is clean (no changes), say something like:
> ✨ Your project is all tidy! Everything is saved. You're ready to start something new!
