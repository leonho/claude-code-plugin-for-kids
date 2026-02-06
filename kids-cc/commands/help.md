---
name: help
description: Show all available commands and learn how to use them
allowed-tools: ""
---

# /kids-cc:help — Your Coding Toolbox

No tools needed — just display this helpful guide in a friendly way!

## What to Show

Present all available commands like a menu in a video game:

```
🧰 **Your Coding Toolbox**

Here's everything you can do! Just type the command to use it.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

💾 /kids-cc:save — **Save your work**
   Creates a save point so you never lose your progress.
   "Like hitting Save in a video game!"

🔍 /kids-cc:status — **Check your project**
   See what files you changed, what's saved, and what's not.

📖 /kids-cc:timeline — **See your project's story**
   A visual timeline of everything you've done.

⏪ /kids-cc:undo — **Undo something**
   Take back your last change — saved or unsaved.
   Don't worry, your work goes to a backup pocket first!

🔄 /kids-cc:restore — **Go back to your last save**
   Throws away unsaved changes and goes back to your last save point.

📦 /kids-cc:recover — **Get work back from backup**
   Pull work out of your backup pocket after an undo or restore.

🤔 /kids-cc:help-me — **Explain an error**
   Got a confusing error? I'll explain it in plain English!

🧰 /kids-cc:help — **You are here!**

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

💡 **Tips:**
- You can always /kids-cc:undo if something goes wrong
- Your work is backed up before any big changes
- I'll never do anything dangerous without asking first
- If you're confused, just ask me anything!
```

## Extra Behavior

- If the user types `/kids-cc:help save` or asks about a specific command, give a more detailed explanation of just that command with an example
- If they seem lost or confused, be extra encouraging: "Don't worry, coding takes practice! You're doing great just by trying. 💪"
- If they ask "what should I do first?", suggest `/kids-cc:status` to see where things stand
- If they ask what a git/coding term means, translate it using the beginner-friendly terms from CLAUDE.md

## Detailed Command Help

If they ask about a specific command, provide a short walkthrough:

### /save
> 💾 **Save** creates a save point — a snapshot of your project right now.
> I'll ask you to describe what you did (like "added the login page"), then save everything.
> **Example:** Type `/kids-cc:save` → I'll show what changed → you write a message → done!

### /undo
> ⏪ **Undo** takes back your last change.
> - If you have unsaved edits, it throws them away (but backs them up first!)
> - If everything is saved, it reverses your last save point
> **Example:** Type `/kids-cc:undo` → I'll show what will be undone → you confirm → done!

### /recover
> 📦 **Recover** gets your work back after an undo or restore.
> Your work is never truly gone — it's in the backup pocket!
> **Example:** Type `/kids-cc:recover` → I'll show your backups → you pick one → it's back!
