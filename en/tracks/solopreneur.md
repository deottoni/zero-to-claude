# Solopreneur Track

You're running this because the user told Claude.md this is just for them — a solo operator. Follow this file start to finish. It refers back to `CLAUDE.md` for the shared master-file spec and completion message — use those, don't rewrite them.

Output folder for this track is **`my-brain/`**.

---

## PHASE 1: Your Context (3 rounds, one at a time)

**CRITICAL RULE: Give ONE round at a time. Never give two rounds in the same message. Always wait for their answer before giving the next one.**

After each answer:
1. Say something encouraging (brief — 1 sentence)
2. Tell them what you're doing with it ("I'm writing your work profile now...")
3. If `output_mode = files`: write/update the relevant file in `my-brain/`
4. If `output_mode = text-blocks`: hold the information and build the full profile at the end of Phase 2
5. Then give the next round

**The prompts live in `/prompts`.** Read and use them exactly as written. Do not paraphrase or shorten them.

| Round | Prompt File | What You Build | File to Create (files mode) |
|-------|-------------|----------------|------------------------------|
| 1 | `prompts/round1-you-and-your-work.md` | Identity, goals, work context | `my-brain/01-you-and-your-work.md` |
| 2 | `prompts/round2-how-you-work.md` | Preferences + working style | `my-brain/02-how-you-work.md` |
| 3 | `prompts/round3-recurring-work-and-projects.md` | Recurring work + current projects | `my-brain/projects/` (one folder + `context.md` per project) |

**If an answer is thin or vague**, say:
> "That gave us a bit less than I'd hoped. Can you answer in your own words? [ask 1-2 short direct follow-ups relevant to that round]. A few sentences is enough — I'll build the rest."

---

### Round 3 special handling — Projects & Tasks

After they answer Round 3:
1. Identify each distinct project or recurring task they mentioned
2. **Files mode:** create a folder for each one inside `my-brain/projects/`, with a `context.md` pre-filled from what you know
3. Show them the folder structure as a simple text list, no jargon
4. Ask: *"I've set up a folder for each of your main work areas. Anything wrong, missing, or named in a way that doesn't feel like you?"*

Example:
```
📁 my-brain/
   📁 projects/
      📁 resume-reviews/
         📄 context.md  ✅ ready
      📁 contract-reviews/
         📄 context.md  ✅ ready
```

---

## PHASE 2: Fill the Gaps

After all 3 rounds are done, check what you already know against this list. **Only ask about what's genuinely still missing** — skip anything already covered:

- Website URL (skip if not relevant to them)
- What they most want Claude to help with day to day
- Anything about AI tools that's annoyed them or not worked
- Short-and-direct vs. detailed-and-thorough preference

If more than one is missing, ask them together in one short message rather than one at a time — this should feel like a quick cleanup, not a fourth round. If everything's already covered, skip Phase 2 entirely and say so briefly before moving on.

---

## PHASE 2 → PHASE 3 GATE

Write `my-brain/CLAUDE.md` using the **master file spec in `CLAUDE.md`**. Show the plain-language summary from that spec and get confirmation before moving on. Do not skip this.

---

## PHASE 3: Build the Personalized Workspace

**Only start after the master file is confirmed.**

Using everything from the 3 rounds, Phase 2, and the master file, identify **3-5 dominant use cases** — the types of work this person actually does most: writing, client work, research, planning, content, teaching, operations, etc.

For each use case, build:

1. **An agent** — a persona/perspective Claude inhabits for that work. Name, short description, perspective, standing instructions, and (per the **model layer spec in `CLAUDE.md`**) a model tier. Opinionated and useful, not generic.
2. **A skill** — a triggered helper for a recurring task. A trigger phrase + structured instructions.
3. **A template** — a starting-point document for a common deliverable, pre-filled with structure and example language.

**Files mode:** write directly — agents → `.claude/agents/[use-case].md` (with `name`/`description`/`model` frontmatter, per the model layer spec — these become real subagents Claude can delegate to), skills → `.claude/skills/[use-case].md`, templates → `templates/[use-case].md`.
**Text-blocks mode:** output each as a formatted block to copy into Project Instructions or save separately, plus the one-line manual model-switching note from the model layer spec.

Reference (guidance, not a checklist — adapt to what this person actually does; model is a starting suggestion, judge it against the model layer spec):

| Use Case | Agent | Model | Skill trigger | Template |
|----------|-------|-------|--------------|----------|
| Writing | editorial-reviewer | sonnet | "review this draft" | email / post / article |
| Client work | client-advisor | sonnet | "prep me for this client" | proposal / follow-up / onboarding |
| Research | research-skeptic | opus | "help me scope this research" | analysis / insight-summary |
| Planning | decision-coach | opus | "help me think through this" | project-brief / decision-memo |
| Content | audience-advisor | sonnet | "brief this content" | caption / newsletter / case study |
| Teaching/coaching | devil's-advocate | sonnet | "prep for this session" | session-notes / feedback |
| Operations | efficiency-advisor | haiku | "break this down" | sop / checklist / runbook |

After generating, show a clean summary — names, model tier, and one-line descriptions of each agent, skill, template. Then say:

> *"Here's what I built for you. These are based on the work you actually described — not generic tools. Let me show you how they work."*

---

## PHASE 3: The Wow Test

Say:
> *"Alright — time to see if this actually works. I'm going to do 3 quick things for you right now. Real things, not demos. Notice what I don't ask you — your name, what you do, how you like things written. I already know. Watch."*

Then immediately do the first task, unprompted:

**Test 1 — The Personalized Message.** Draft a short message on their behalf (follow-up email, client note, quick pitch — whatever fits their real work), in their voice, using real context. Don't ask permission — write it and show it. Then: *"I wrote that without asking you a single thing. Does it sound like you?"*

**Test 2 — The Agent.** *"I built an advisor who thinks like [perspective], running on [model tier] since that's the right fit for this kind of work. Let me show you."* **Files mode:** actually delegate to that subagent for a realistic scenario, so it runs for real on its assigned model. **Text-blocks mode:** step into that voice yourself, since there's no subagent to delegate to. Then: *"That's your [agent name]. Notice anything different?"*

**Test 3 — The Skill.** *"You said you [do X] regularly. Say '[trigger phrase]' and watch what happens."* Wait for the phrase, execute the skill as designed. Then: *"That's your [skill name] skill. One phrase, every time."*

After all 3: *"Out of those 3 — did any feel like it really knew you? Anything feel off?"*

If something's off, fix the relevant file. Otherwise, give the **completion message from `CLAUDE.md`**, filling in the actual counts of what was built.
