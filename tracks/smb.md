# SMB Track

You're running this because the user told CLAUDE.md this is for a team or small business, not just themselves. Follow this file start to finish. It refers back to `CLAUDE.md` for the shared master-file spec and completion message — use those, don't rewrite them.

Output folder for this track is **`company-brain/`** (parallel to `my-brain/` in the solopreneur track — same idea, scoped to the business rather than one person).

---

## PHASE 1: Your Context (4 rounds, one at a time)

**CRITICAL RULE: Give ONE round at a time. Never give two rounds in the same message. Always wait for their answer before giving the next one.**

After each answer:
1. Say something encouraging (brief — 1 sentence)
2. Tell them what you're doing with it
3. If `output_mode = files`: write/update the relevant file in `company-brain/`
4. If `output_mode = text-blocks`: hold the information and build the full profile at the end of Phase 2
5. Then give the next round

**The prompts live in `/prompts`.** Read and use them exactly as written. Rounds 1-3 are answered from the perspective of the person setting this up (usually the owner/founder); Round 4 is about the business as a whole.

| Round | Prompt File | What You Build | File to Create (files mode) |
|-------|-------------|----------------|------------------------------|
| 1 | `prompts/round1-you-and-your-work.md` | Founder/owner identity, goals, business context | `company-brain/01-you-and-your-work.md` |
| 2 | `prompts/round2-how-you-work.md` | Preferences + working style | `company-brain/02-how-you-work.md` |
| 3 | `prompts/round3-recurring-work-and-projects.md` | Recurring work + current projects | `company-brain/projects/` (one folder + `context.md` per project) |
| 4 | `prompts/round4-smb-team-and-functions.md` | Team shape + priority functions | `company-brain/03-team-and-functions.md` |

**If an answer is thin or vague**, say:
> "That gave us a bit less than I'd hoped. Can you answer in your own words? [ask 1-2 short direct follow-ups relevant to that round]. A few sentences is enough — I'll build the rest."

Round 3's folder handling is the same as the solopreneur track — a folder per project/recurring task inside `company-brain/projects/`, shown back to the user as a simple list for confirmation.

### Round 4 special handling

From the answer, extract:
- `team_summary` — who's on the team, roughly
- `decision_style` — centralized or distributed
- `priority_functions` — the 2-4 functions they flagged (sales, marketing, ops, HR, finance, support, data/reporting, etc.)
- for each priority function, the specific bottleneck they described

This list of `priority_functions` is what Phase 3 builds agents around — it replaces the "3-5 dominant use cases" step from the solopreneur track. Don't ask them to separately describe use cases; the functions they already named **are** the use cases.

---

## PHASE 2: Fill the Gaps

After all 4 rounds, check what you already know against this list. **Only ask about what's genuinely still missing:**

- Website URL (skip if not relevant)
- What they most want Claude to help with day to day
- Anything about AI tools that's annoyed them or not worked
- Short-and-direct vs. detailed-and-thorough preference

If more than one is missing, ask together in one short message, not one at a time. If everything's covered, skip Phase 2 and say so briefly.

---

## PHASE 2 → PHASE 3 GATE

Write `company-brain/CLAUDE.md` using the **master file spec in `CLAUDE.md`** — "Who I Am" becomes the business + founder, "My Work Areas" includes both projects and the priority functions. Show the plain-language summary and get confirmation before moving on. Do not skip this.

---

## PHASE 3: Build the Company Workspace

**Only start after the master file is confirmed.**

For each of the `priority_functions` identified in Round 4 (2-4 of them), build:

1. **An agent** — a business-function advisor Claude inhabits when working on that function. Name, short description, perspective, standing instructions, a model tier (per the **model layer spec in `CLAUDE.md`**), and — critically — grounded in the *specific bottleneck* they described for that function, not a generic version.
2. **A skill** — a triggered helper for the most recurring task in that function.
3. **A template** — a starting-point document for that function's most common deliverable.

**Files mode:** write directly — agents → `.claude/agents/[function].md` (with `name`/`description`/`model` frontmatter, per the model layer spec — these become real subagents Claude can delegate to, so a heavier function like finance genuinely runs on a stronger model), skills → `.claude/skills/[function].md`, templates → `templates/[function].md`.
**Text-blocks mode:** output each as a formatted block to copy into Project Instructions or save separately, plus the one-line manual model-switching note from the model layer spec.

Use this as a starting point for naming, shape, and model tier — adapt freely to what they actually described, don't force a function into a mold that doesn't fit:

| Function | Agent | Model | Skill trigger | Template |
|----------|-------|-------|--------------|----------|
| Leadership / CEO | ceo-advisor | opus | "help me think through this decision" | decision-memo |
| Ops | ops-manager | sonnet | "break this process down" | sop / runbook |
| Marketing | marketing-strategist | sonnet | "brief this campaign" | content-brief / caption / newsletter |
| Sales | sales-coach | sonnet | "prep me for this call" | pitch / follow-up / proposal |
| HR / People | hr-partner | sonnet | "help me handle this people issue" | job-post / feedback-doc / policy-note |
| Finance | finance-analyst | opus | "sanity-check these numbers" | budget-summary / forecast-note |
| Customer support | support-lead | haiku | "draft this response" | reply-template / escalation-note |
| Data / reporting | data-analyst | opus | "help me read this data" | analysis-summary |

After generating, show a clean summary — names, model tier, and one-line descriptions of each agent, skill, template, tied back to the bottleneck each one addresses. Then say:

> *"Here's what I built for you. Each one is aimed at the specific bottleneck you described — not a generic tool. Let me show you how they work."*

### Setting up the team

**Nobody else on the team needs to run this whole setup.** One person (usually the owner or an admin) builds the company brain once. Everyone else "hooks up" to it — but how they do that depends on which Claude surface they're on, and the three surfaces are not equally capable today. Say this plainly rather than glossing over it — it's a real decision, not a footnote:

> *"Quick but important thing: how your team shares this depends on where they use Claude. It's not the same everywhere yet — let me walk you through it so you pick the right one."*

**Claude Code — the go-to if anyone on the team is comfortable with git.** This is the most complete option today, because Claude Code already has a built-in split that matches "company brain + personal brain" exactly:
- *Shared, repo-level:* `company-brain/`, `.claude/agents/`, `.claude/skills/`, `templates/` — everything this setup just built. Put it in a **private GitHub (or GitLab) repo**. Anyone who clones that repo automatically gets the same brain, the same agents, the same skills — that's the entire "hook up" step, nothing else to configure.
- *Personal, user-level:* `~/.claude/CLAUDE.md` and `~/.claude/agents/` / `~/.claude/skills/` on each person's own machine — private to them, and layered on top of every project they open, including this shared one. Each teammate can optionally set this up for themselves (a short personal pass, not the full setup) so Claude also knows *them*, not just the company.
- Recommend this path for whoever's technical enough (ops especially).

**claude.ai — works, but it's a plan decision, not just a technical one.** Team and Enterprise plans support real shared Projects: an admin creates one Project, uploads the company-brain files as Project knowledge, pastes the company instructions in as Project Instructions, then invites teammates as either "Can Use" (chat + view, can't edit) or "Can Edit." Teammates don't set anything up — they accept an invite and start chatting inside that shared Project. The consideration to flag clearly: **this needs a paid Team or Enterprise plan, per seat** — for a 5-8 person company that's a real cost conversation, not a free feature. Good default for non-technical roles (admin, marketing, sales) once that's decided.

**Cowork — not there yet for a shared team brain.** Say this directly, don't oversell it: *Cowork sessions and workspaces can't be shared between people today* — you can share an individual artifact you made, but not a live shared workspace, knowledge base, or brain. The team mechanism Cowork does have is **Plugins** (bundles of skills/connectors/sub-agents an admin can publish to a private org marketplace for teammates to install), but that distributes *capabilities*, not the company's actual knowledge/context the way a shared repo or shared claude.ai Project does. **Right now, recommend Cowork only for solopreneurs, not as the shared layer for a team** — revisit this once Anthropic ships real workspace sharing there.

**Mixed team (most common case):** since everything this setup produces is plain text/markdown, you're not locked into one surface. Keep the source of truth in one private repo either way, then deploy the same content per person — Claude Code teammates clone the repo directly; claude.ai teammates get the same content pasted into the shared Project; Cowork users, for now, are the exception to plan around rather than solve.

Don't attempt to solve deeper integrations here (connecting the company's other tools, single sign-on, that kind of thing) — that's a separate, deeper topic Andre covers elsewhere. This section's job is just making sure the team ends up on the same brain, on whichever surface actually works for that.

---

## PHASE 3: The Wow Test

Say:
> *"Alright — time to see if this actually works. I'm going to do 3 quick things for you right now. Real things, not demos. Notice what I don't ask you — your name, what your business does, how you like things written. I already know. Watch."*

Then immediately do the first task, unprompted:

**Test 1 — The Personalized Message.** Draft a short message on their behalf tied to the real business (a client note, a team update, a quick pitch), in their voice, using real context. Don't ask permission — write it and show it. Then: *"I wrote that without asking you a single thing. Does it sound like your business?"*

**Test 2 — The Agent.** *"I built a [function] advisor grounded in the bottleneck you described, running on [model tier]. Let me show you."* **Files mode:** actually delegate to that subagent for a realistic scenario from that function, so it runs for real on its assigned model. **Text-blocks mode:** step into that voice yourself, since there's no subagent to delegate to. Then: *"That's your [agent name]. Notice anything different?"*

**Test 3 — The Skill.** *"You said [bottleneck] is a real pain point. Say '[trigger phrase]' and watch what happens."* Wait for the phrase, execute the skill as designed. Then: *"That's your [skill name] skill. One phrase, every time."*

After all 3: *"Out of those 3 — did any feel like it really understood the business? Anything feel off?"*

If something's off, fix the relevant file. Otherwise, give the **completion message from `CLAUDE.md`**, filling in the actual counts of what was built.
