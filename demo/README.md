# Demo Mode — for Andre only

This folder is not part of what a client gets. It's how you run a confident, repeatable live demo of Zero to Claude — the **real flow**, with a **made-up client** answering, so nothing here is a mockup and nothing here is a real person's data.

## Why this exists

The framework already has a built-in "wow test" at the end of each track — that's the actual payoff moment. What was missing was a safe way to *get there* live, in front of someone, without needing a real client's real answers on the spot. This solves that: two ready-made personas you can paste in, plus a run-of-show sheet so you're not just narrating a wall of chat text.

## How to run it

**Always open Claude Code at the repo root (`zero-to-claude/`), not this `/demo` folder.** `CLAUDE.md` — the file Claude Code reads automatically — lives at the root. `/demo` has no entry point of its own; it's just where the persona files live for you to copy from in a separate window while the session runs at the root.

There are two ways to run it, depending on whether you want to show real files being created:

### Option A — zero footprint (default, safest, works in your real cloned repo)

Open the real repo in Claude Code as usual and say "let's go." When Claude asks Phase 0's second question ("can I create and edit files here?"), **answer no** — that forces text-blocks mode, so Claude prints everything in the chat instead of writing to disk. Nothing gets created, nothing to clean up, no risk to the repo you'd hand a real client. The one thing you lose: the "watch it create real files/folders live" beat, and the agent in the Wow Test becomes a roleplay rather than a real subagent delegation.

### Option B — real files, for when you want to show the file-creation moment

Copy the repo to a scratch folder first, and run the demo there instead of your real clone. Naming it with today's date makes it obvious later which ones are safe to delete:
```
cp -r zero-to-claude ~/Desktop/demo-$(date +%m-%d-%y)
cd ~/Desktop/demo-$(date +%m-%d-%y)
```
Open that copy in Claude Code and answer **yes** to the file-access question. This gets you the full effect — real folders appearing, real subagent delegation with its actual model tier in the Wow Test. When you're done, just delete the dated folder — anything named `demo-*` on your Desktop is always safe to remove.

### Either way

1. Open the **[rundown sheet](https://claude.ai/code/artifact/cbcf8b0b-8a44-4ca6-9293-c283f149cc4b)** on a second screen or window — it's your run-of-show while you talk. Toggle Solopreneur/SMB at the top to match whichever persona you're running.
2. Answer Phase 0's track question: **solopreneur** → use `personas/solopreneur-demo.md`, or **team/small business** → use `personas/smb-demo.md`.
3. For each round, open the matching persona file and paste that round's answer block when Claude gives you the prompt. Don't read the whole file live — it's pre-split by round so you just copy the next block each time.
4. Let the Wow Test run for real — this is the actual product working, not a script for that part.

## What's in here

| File | What it's for |
|------|---------------|
| `personas/solopreneur-demo.md` | Jordan Reyes, independent marketing consultant — canned answers for the solopreneur track |
| `personas/smb-demo.md` | Bright Leaf Coffee Co., a 7-person specialty coffee business — canned answers for the SMB track |

Both personas are deliberately realistic and specific (not generic placeholder text) so the Wow Test actually lands — a vague fake persona produces a vague, unconvincing demo.
