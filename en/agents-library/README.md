# agents-library/

Starting-point templates for the SMB track's 8 business-function agents — not generic filler, the
same 8 functions and model tiers already named in `../tracks/smb.md`'s reference table (Leadership,
Ops, Marketing, Sales, HR, Finance, Support, Data).

**How this is used during onboarding:** when the SMB track identifies a priority function, Claude
copies the matching file here into `.claude/agents/[function].md`, then **tailors it** — folds in
the specific bottleneck the person described, their business's real context, their team's names
if relevant — rather than generating an agent from a blank page. The persona, scope, and standing
instructions in each file here are a solid, opinionated default; the tailoring pass is what makes
the result feel built for *this* business instead of copy-pasted.

Each file is real, minimal `.claude/agents/*.md` frontmatter (`name`/`description`/`model`) plus a
persona, a scope line (what it's for and what it isn't), a short "how you work" list, and 2-3
example prompts — deliberately not the sprawling, tool-by-tool capability lists you'll find in
big open-source subagent collections. These are for small teams, not enterprises: an SMB owner
needs an agent that gives good, specific help fast, not one that name-drops a BI stack they'll
never touch.
