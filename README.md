# Zero to Claude — Setup Framework
by [Andre Ottoni](https://andreottoni.com)

---

## What this is

A guided setup that gives Claude a complete picture of who you are before your first real conversation. By the end, Claude knows your background, goals, working style, and the specific work you do — so you never have to re-explain yourself.

**What you walk away with:**
- A personal profile Claude reads at the start of every session
- Work folders for your recurring tasks, pre-loaded with context
- Agents built around your dominant use cases (a perspective Claude inhabits for that type of work)
- Skills that trigger structured help for the things you do most
- Templates for your most common deliverables
- A voice guide so responses always sound right for you

The whole setup takes about 45–60 minutes.

---

## Two ways to use this

### Option A — claude.ai (browser or app)

Best if you want a conversational setup and plan to use Claude through the website or app.

1. Go to [claude.ai](https://claude.ai) and create a new Project
2. Open `CLAUDE.md` from this folder and paste its entire contents into the Project Instructions
3. Upload the files in `prompts/` as Project knowledge
4. Start a conversation — Claude will greet you and walk you through everything

When setup is complete, Claude outputs structured text blocks you can save back into Project Instructions to keep your profile current.

### Option B — Claude Code

Best if you want the full file-based system, with agents, skills, and templates written directly to this folder.

1. Open this folder in Claude Code (`claude /path/to/zero-to-claude`)
2. `CLAUDE.md` is read automatically — Claude will greet you on first message
3. Work through the setup; Claude writes files as you go

When setup is complete, Claude writes agents to `.claude/agents/`, skills to `.claude/skills/`, and templates to `templates/` — ready to use in future sessions.

**Not sure which to pick?** Use claude.ai if you want to chat. Use Claude Code if you want the full file-based system.

---

## Visual guide

**Live:** [deottoni.github.io/zero-to-claude](https://deottoni.github.io/zero-to-claude/)

Or open `index.html` locally — double-click the file or drag it into any browser. No install needed.

---

## What's in this folder

| File/Folder | What it is |
|-------------|------------|
| `CLAUDE.md` | Instructions that run the guided setup |
| `index.html` | Visual step-by-step reference — open in browser or visit the link above |
| `prompts/` | The 6 context prompts |
| `templates/` | Generated post-onboarding (populated during setup) |
| `.claude/agents/` | Generated agents — Claude Code only |
| `.claude/skills/` | Generated skills — Claude Code only |

After setup, Claude creates a `my-brain/` folder with your personal profile files. That's your AI brain — keep this folder safe and use it as your project going forward.

---

## Questions?
[andreottoni.com](https://andreottoni.com)
