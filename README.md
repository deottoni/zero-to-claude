# Zero to Claude — Setup Framework
by [Andre Ottoni](https://andreottoni.com)

---

## What this is

A guided setup that gives Claude a complete picture of who you are — or who your business is — before your first real conversation. By the end, Claude knows your background, goals, working style, and the specific work you do, so you never have to re-explain yourself.

Everything you need is in this folder. There's no separate app, tracker, or webpage to keep open — you open this folder in Claude, and Claude runs the whole thing conversationally from `CLAUDE.md`, start to finish. Takes about 30-45 minutes.

There are two tracks:

- **Solopreneur** — you're a solo operator. You get a personal profile ("brain"), agents and skills built around your actual work, and templates for what you make most.
- **SMB** — this is for a team or small business. You get the same idea, scoped to the business: a shared company profile, plus agents built around the specific functions (sales, ops, marketing, HR, etc.) where you said AI could help most.

You don't need to pick a track yourself — Claude asks at the start and takes it from there.

---

## How to run it

1. Get this folder onto your machine — clone this repo, or download it as a ZIP and unzip it.
2. Open it in whichever Claude surface you use:
   - **Claude Code** — open the folder in your terminal (`claude /path/to/zero-to-claude`)
   - **Cowork** — open the folder as a workspace
   - **claude.ai** (browser or app) — create a new Project, paste the entire contents of `CLAUDE.md` into the Project Instructions, and upload everything in `/prompts` and `/tracks` as Project knowledge
3. Say "hi" or "let's go." Claude reads `CLAUDE.md`, asks two quick questions (which track, and whether it can write files here), and runs the rest of the setup with you.

That's it. Claude tracks where you are in the process itself — there's nothing to check off anywhere else.

**If you're in Claude Code or Cowork**, Claude writes your profile, agents, skills, and templates directly into this folder as you go. **If you're on claude.ai**, Claude gives you clearly labeled text you copy into your Project's Instructions or knowledge instead — same outcome, just no local files.

---

## Optional: visual preview

**Live:** [deottoni.github.io/zero-to-claude](https://deottoni.github.io/zero-to-claude/)

`index.html` is a short preview of what the setup covers and what you walk away with. It's entirely optional — you never need to open it to actually do the setup, and it doesn't track your progress. Claude does that in conversation.

---

## What's in this folder

| File/Folder | What it is |
|-------------|------------|
| `CLAUDE.md` | The master file — Claude reads this first, asks your two starting questions, and hands off to the right track |
| `tracks/solopreneur.md` | The full flow for a solo operator |
| `tracks/smb.md` | The full flow for a team / small business |
| `prompts/` | The 3-4 context-gathering prompts used by both tracks |
| `templates/` | Generated after setup — starting points for your most common deliverables |
| `.claude/agents/` | Generated agents — Claude Code / Cowork only |
| `.claude/skills/` | Generated skills — Claude Code / Cowork only |
| `index.html` | Optional visual preview — not required to run the setup |

After setup, you'll have a `my-brain/` folder (solopreneur) or `company-brain/` folder (SMB) with your profile files. That's your AI brain — keep it safe and use it as your project going forward.

---

## Questions?
[andreottoni.com](https://andreottoni.com)
