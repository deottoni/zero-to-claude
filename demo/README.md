# Demo Mode — for Andre only

## Instructions for Claude: you were sent here because the person running this said something like "run the demo." Follow this file, not the normal `CLAUDE.md` flow. Everything below is written for you to execute, not for a human to read and act on step by step — the whole point is that Andre shouldn't have to remember commands, folders, or which file to open.

This is the **real flow**, with a **made-up client** answering, so nothing here is a mockup and nothing here is a real person's data. It exists so Andre can rehearse or present confidently without needing a real client's real answers on the spot, and without having to think about setup mechanics himself.

---

## Step 1 — ask how to run it

Ask, in one message:

> *"Quick setup for the demo: should I actually create real files and folders — the full effect — or just play it out here in the chat with nothing saved anywhere? And which one do you want to run: the solopreneur (Jordan Reyes) or the small business (Bright Leaf Coffee Co.)?"*

Wait for both answers before doing anything else.

### If they want real files

Run this yourself (you have shell access — just do it, don't ask them to run anything):

```
cp -r [this repo's root folder] ~/Desktop/demo-$(date +%m-%d-%y)
```

Then tell them plainly: *"Copied to `~/Desktop/demo-MM-DD-YY` — I'll do everything from there, your real repo is untouched. Safe to delete that whole folder when we're done."* From this point on, treat that copied path as the project root for every file you read or write for the rest of this session — use full paths to it, don't assume your working directory moved. Set `output_mode = files`.

### If they want chat-only (no files)

Say so back to confirm: *"Got it — nothing gets saved, this all just plays out here."* Set `output_mode = text-blocks` and never call a file-write tool for the rest of the demo, even though you technically could. This is safe to run directly in the real repo, exactly where you are right now.

---

## Step 2 — load the track and the persona

Based on which persona they picked:
- **Jordan Reyes** → track = solopreneur → persona file `demo/personas/solopreneur-demo.md`
- **Bright Leaf Coffee Co.** → track = smb → persona file `demo/personas/smb-demo.md`

Read the whole persona file now. Then say:

> *"Rundown's here if you want it on a second screen: [Live Demo Rundown](https://claude.ai/code/artifact/cbcf8b0b-8a44-4ca6-9293-c283f149cc4b) — toggle it to [solopreneur/SMB]. Ready when you are — just say 'go' and I'll start."*

Wait for them to say go.

---

## Step 3 — run the real track, feeding yourself the persona's answers

Follow `CLAUDE.md`'s shared spec and `tracks/solopreneur.md` or `tracks/smb.md` **exactly as written**, with two differences from a normal run:

1. **Don't run Phase 0's question or its self-detection step again.** Track and `output_mode` are already decided from Step 1 above — and Step 1's answer wins even if it disagrees with what your own self-detection would conclude (e.g. they may ask for chat-only even though you technically could write files, precisely so nothing gets saved). Skip straight into the welcome beat and Round 1.
2. **Don't wait for the human to type or paste an answer to each round.** When the track file says to give a round's prompt, give it out loud as normal (for narration), then immediately answer it yourself using that round's block from the persona file you already read — as if the persona had just said it. **Then pause and wait for the presenter to say "next" or "go" before moving to the following round** — they need room to narrate over the rundown sheet, so don't auto-chain through every round back to back.

Everything else runs for real: file writes (if in files mode), the mandatory confirmation gate, the Phase 3 build with real model tiers, and the Wow Test. Don't script or shortcut the Wow Test — that's the actual product working, and it should run exactly as `tracks/*.md` defines it.

---

## Step 4 — after the Wow Test

Give the normal completion message from `CLAUDE.md`. Then, only if you ran in files mode, remind them once: *"Everything's in `~/Desktop/demo-MM-DD-YY` — delete that folder whenever, your real repo was never touched."*

---

## Reference — what's in this folder

| File | What it's for |
|------|---------------|
| `personas/solopreneur-demo.md` | Jordan Reyes, independent marketing consultant — canned answers for the solopreneur track |
| `personas/smb-demo.md` | Bright Leaf Coffee Co., a 7-person specialty coffee business — canned answers for the SMB track |

Both personas are deliberately realistic and specific (not generic placeholder text) so the Wow Test actually lands — a vague fake persona produces a vague, unconvincing demo.
