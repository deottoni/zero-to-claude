# Demo Mode — for Andre only

This folder is not part of what a client gets. It's how you run a confident, repeatable live demo of Zero to Claude — the **real flow**, with a **made-up client** answering, so nothing here is a mockup and nothing here is a real person's data.

## Why this exists

The framework already has a built-in "wow test" at the end of each track — that's the actual payoff moment. What was missing was a safe way to *get there* live, in front of someone, without needing a real client's real answers on the spot. This solves that: two ready-made personas you can paste in, plus a run-of-show sheet so you're not just narrating a wall of chat text.

## How to run it

1. **Copy the repo to a scratch folder** — never run the demo inside the real cloned repo you'd hand to a client:
   ```
   cp -r zero-to-claude ~/Desktop/zero-to-claude-demo
   cd ~/Desktop/zero-to-claude-demo
   ```
2. Open that copy in Claude Code (or paste `CLAUDE.md` into a fresh claude.ai Project if you're demoing that path instead).
3. Open the **[rundown sheet](https://claude.ai/code/artifact/cbcf8b0b-8a44-4ca6-9293-c283f149cc4b)** on a second screen or window — it's your run-of-show while you talk. Toggle Solopreneur/SMB at the top to match whichever persona you're running.
4. Say "let's go." When Claude asks its two Phase 0 questions, answer:
   - Track: **solopreneur** → use `personas/solopreneur-demo.md`, or **team/small business** → use `personas/smb-demo.md`
   - File access: answer honestly for whatever you actually opened it in
5. For each round, open the matching persona file and paste that round's answer block when Claude gives you the prompt. Don't read the whole file live — it's pre-split by round so you just copy the next block each time.
6. Let the Wow Test run for real — this is the actual product working, not a script for that part.
7. **When you're done, just delete the scratch folder.** Nothing here ever touches your real repo, and nothing fake ever ships to a client.

## What's in here

| File | What it's for |
|------|---------------|
| `personas/solopreneur-demo.md` | Jordan Reyes, independent marketing consultant — canned answers for the solopreneur track |
| `personas/smb-demo.md` | Bright Leaf Coffee Co., a 7-person specialty coffee business — canned answers for the SMB track |

Both personas are deliberately realistic and specific (not generic placeholder text) so the Wow Test actually lands — a vague fake persona produces a vague, unconvincing demo.
