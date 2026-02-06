---
name: timeline
description: See your project's story — a visual timeline of all your save points
allowed-tools: Bash(git log), Bash(git shortlog)
---

# /kids-cc:timeline — Your Project's Story

Show a fun, visual timeline of the project's save history. This is like reading a diary of everything that happened!

## Steps

1. **Get the visual log** — Run `git log --oneline --graph --decorate --all -20`
2. **Get save point count** — Run `git log --oneline | wc -l`
3. **Get contributor summary** — Run `git shortlog -sn --all`
4. **Present it beautifully**

## How to Present

Transform the raw git log into a friendly timeline. Use this format:

```
📖 **Your Project's Story** (X save points total)

🕐 **Today**
  💾 Added the cool animation
  💾 Fixed the button color

🕐 **Yesterday**
  💾 Created the login page
  💾 Started the project

👤 **Builders:** You (and anyone else who contributed)
```

### Rules for Presentation

- Group save points by **day** (Today, Yesterday, 2 days ago, last week, etc.) — use relative time
- Show the save point **message**, not the hash
- Use 💾 for regular save points
- Use 🔄 for undo/revert save points
- Use 🎉 for the very first save point ("This is where it all began!")
- If there are branches, mention them: "You have X versions of your project"
- Cap at 20 save points — if there are more, say "...and X more save points before that!"
- Show total count and contributors at the bottom

## Example Output

> 📖 **Your Project's Story** — 12 save points total
>
> 🕐 **Today**
> - 💾 Added dark mode toggle
> - 💾 Fixed the navbar spacing
> - 🔄 Undid "broke the footer" (phew!)
>
> 🕐 **Yesterday**
> - 💾 Built the contact form
> - 💾 Added form validation
>
> 🕐 **Last week**
> - 💾 Created the about page
> - 💾 Added the homepage hero
> - 💾 Set up the project structure
> - 🎉 First save point — this is where it all began!
>
> 👤 **Builders:** You
> 📊 **Total:** 12 save points over 8 days. You've been busy! 🚀
