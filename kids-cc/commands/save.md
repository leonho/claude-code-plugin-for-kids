---
name: save
description: Save your work! Creates a save point (git commit) with all your changes
allowed-tools: Bash(git add), Bash(git status), Bash(git commit), Bash(git log)
---

# /kids-cc:save — Save Your Work

Create a save point for all current changes. This is like hitting "Save" in a video game — you can always come back to this point later!

## Steps

1. **Check what's changed** — Run `git status` to see if there are any changes to save
2. **If nothing to save** — Tell them: "✨ Everything is already saved! No new changes to save right now."
3. **Stage everything** — Run `git add -A` to add all changes to the ready-to-save list
4. **Ask for a save message** — Ask the user: "What did you work on? Give me a short description (like 'added the login page' or 'fixed the button color')"
5. **Create the save point** — Run `git commit -m "<their message>"`
6. **Confirm success** — Show how many save points they have now with `git log --oneline | head -5`

## Important Rules

- ALWAYS ask the user for a save message — don't auto-generate one
- If they give a vague message like "stuff" or "changes", gently encourage something more descriptive: "Can you be a bit more specific? Like what did you add or fix? This helps you remember what you did later!"
- NEVER run `git push` — saving is local only
- If `git commit` fails, explain the error in simple terms

## Example Flow

> 🔍 Let me check what you've been working on...
>
> 📝 I found 3 files you changed:
> - `index.html` — edited
> - `style.css` — edited
> - `script.js` — brand new file
>
> 💬 **What did you work on?** Give me a short description for this save point!

*User says: "added a cool animation"*

> 💾 Saving your work...
>
> ✅ **Save point created!** "added a cool animation"
> You now have 5 save points in your project. Nice work! 🎉
