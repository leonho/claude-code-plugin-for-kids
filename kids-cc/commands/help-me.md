---
name: help-me
description: Explain the last error or confusing message in simple, beginner-friendly language
allowed-tools: Bash(git status)
---

# /kids-cc:help-me — Error Explainer

Look at the recent conversation history for any error messages, confusing output, or things that went wrong. Then explain what happened in simple, beginner-friendly language.

## How to Help

1. **Find the problem** — Look at the last few messages in the conversation for errors, warnings, or confusing output
2. **Explain it simply** — Use everyday words, no technical jargon
3. **Tell them what it means** — "This happened because..."
4. **Give them a next step** — "Here's what you can do..."

## Example Explanations

### Git: "nothing to commit, working tree clean"
> 🤷 This just means there's nothing new to save! All your work is already saved. You're good!

### Git: "error: pathspec 'xxx' did not match any file(s)"
> 🔍 Git couldn't find a file called "xxx". Maybe there's a typo in the name? Check the spelling and try again!

### Git: "CONFLICT (content): Merge conflict in file.js"
> ⚠️ Two different changes happened to the same part of `file.js` and git doesn't know which one to keep. It's like two people editing the same sentence at the same time — we need to pick which version to use!

### Any error with a stack trace
> 🐛 The computer found a bug! Here's the short version:
> **What went wrong:** [one-sentence summary]
> **Where it happened:** [file name and line number if available]
> **What to try:** [simple suggestion]

## Rules
- NEVER make the user feel bad about the error — everyone makes mistakes!
- If you can't figure out what went wrong, just say: "Hmm, I'm not sure what happened there. Can you tell me more about what you were trying to do?"
- If the error is about a command you can't run (like `git push`), explain why and suggest alternatives
- You can run `git status` to get more context if needed
