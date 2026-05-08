# Getting Started

Read this end-to-end before you start. The whole setup takes about 90 minutes if you go deep.

---

## Step 1: Place the folder

Copy this whole `agent-os-starter/` folder to where you want your HQ to live. Recommended:

```bash
cp -r agent-os-starter ~/HQ
cd ~/HQ
```

From here on, `~/HQ/` is your headquarters. Every reference in this kit assumes that path.

---

## Step 2: Set up your two inboxes (alongside HQ)

This is the **physical bridge** between you and your AI. Two folders, both at the same level as HQ — not inside it.

```bash
mkdir -p ~/Inbox
mkdir -p ~/"Owner's Inbox"
```

### `~/Inbox/` — your drop zone TO the AI

Anything you want AI to see, read, process, or act on goes here.

- Photos of receipts and invoices
- PDFs to summarise
- Voice memos to transcribe
- Screenshots of conversations
- Notes you scribbled and want filed
- Files a colleague sent you that need triaging

The AI's standing instruction is: **check `~/Inbox/` at the start of any session where the user asks "what's in my inbox?" or "process my inbox."** Files get read, content gets routed to the right place in HQ (or filed in the relevant entity), and the original is moved to `~/History/` (see Step 3).

### `~/Owner's Inbox/` — the AI's delivery zone TO you

Anything the AI produces that needs your eyes before it's "done" goes here. This is where AI drops:

- Draft emails awaiting your approval before sending
- Meeting briefs the night before
- Daily/weekly summaries
- Research briefs from your research agent
- Proposals, scripts, social posts — all in DRAFT
- Anything flagged for your decision

The rule: **AI never sends, posts, or commits anything from this folder. You are the gatekeeper.** You review, edit, approve, and either action it yourself or hand it back to the AI with explicit "send this" / "post this" instructions.

This separation matters. Without it, AI either bothers you constantly with permission requests, or starts acting unilaterally. With it, you have a tray you check on your own schedule and the AI works async without blocking on you.

---

## Step 3: Set up History (where deleted things go to die)

```bash
mkdir -p ~/History/{Archives,RedTag,Backups,Desktop,Downloads,Screenshots}
```

The rule: **AI never deletes files. It moves them to `~/History/RedTag/`.** If something turns out to have been needed, you can fish it out. If it never gets retrieved in 90 days, it's safe to actually delete.

This one rule alone has saved many a panic.

---

## Step 4: Open Claude Code in your HQ

Make sure Claude Code is installed (`npm install -g @anthropic-ai/claude-code` or follow current install instructions), then:

```bash
cd ~/HQ
claude
```

Claude Code will auto-load `CLAUDE.md` from this folder. That file tells it how to navigate everything in here.

---

## Step 5: Run the interview

Paste the prompt below into Claude Code. It will interview you for 30-60 minutes and then populate your core context files.

```
I want you to interview me to populate my HQ context docs. Specifically:
- master-context.md (who I am, what I do, voice, approval rules)
- CURRENT.md (current focus, this week, open questions)
- entity-structure.md (my businesses, trusts, brands, projects)
- people/ (start files for the 5-10 most important people in my orbit)
- glossary.md (shorthand and acronyms I use)

Rules for the interview:
1. Ask ONE question at a time. Wait for my answer before moving on.
2. Don't accept vague answers. If I say "I help businesses with marketing,"
   ask what kind, who specifically, what outcome.
3. Reflect back what you've heard every 4-5 questions to check you've got
   it right. Correct yourself if I push back.
4. Group questions into phases. Tell me when we're moving phases.
5. Don't write any files until we've been through all phases — then write
   everything in one batch and show me the diffs.

Phases:
A. Identity — name, role, location, day-to-day work, what I'm known for.
B. Entities — every business, brand, trust, or project I run. For each:
   what it does, who it serves, status, my role.
C. People — partners, co-founders, team, key clients, mentors. Who do
   I talk to most? Who do I rely on?
D. Goals — what am I trying to accomplish in the next 90 days? 12 months?
E. Voice & style — Australian/American/British English? Direct or warm?
   Phrases I use a lot? Phrases I never use?
F. Approval rules — what should AI never do without asking me?
G. Workflow — when do I work? Morning person? Want briefs before a
   certain time? Mobile or desktop primary?
H. Shorthand — acronyms, codenames, internal language an outsider
   wouldn't get.

Start with phase A, question 1. Go.
```

When the interview's done, Claude Code writes everything in one batch. Read the diffs. Edit anything that doesn't sound like you. **The voice in `master-context.md` is the voice every AI agent will write in from now on, so make it sound exactly like you.**

---

## Step 6: Decide what NOT to install yet

A trap people fall into: trying to set up everything on day one (databases, integrations, custom skills, multi-agent orchestration). Don't.

For week 1, you only need:

- This folder filled in
- `~/Inbox/` and `~/Owner's Inbox/` working
- Claude Code reading this folder

Run that for a week. Pay attention to what's missing. *Then* extend.

Common day-30 additions:
- A skills repo for reusable capabilities
- An MCP connection to your calendar or email
- A second harness (e.g. ChatGPT desktop reading the same files)
- More entities and playbooks as the patterns emerge

---

## Step 7: Build your first playbook

Pick one repeatable task you do every week (e.g. weekly review, sales call follow-up, content posting routine). Write it as a playbook in the relevant entity folder. Use this format:

```yaml
---
title: "Weekly Review Playbook"
entity: shared
type: playbook
tags: [weekly, review]
updated: 2026-Jan-15
---
```

Then the body — what triggers it, what the steps are, what the output is, what to hand to AI vs do yourself. See `example-entity/playbooks/ex-onboarding-playbook.md` for the shape.

Once you have 3-5 playbooks, the system starts compounding — AI knows exactly how to help with the things you do most.

---

## Common questions

**"Should I track this folder in git?"**
Yes. Make it a private repo (GitHub, GitLab, wherever). It's your operating brain — version-controlled is non-negotiable. Just keep secrets, .env, and anything personal-confidential out (the included `.gitignore` patterns are a starting point — adjust to fit).

**"What about my journal — markdown or database?"**
Start in markdown (`journal/YYYY-Mon-DD.md`). When you outgrow it, mirror to a database. The markdown stays as offline backup forever.

**"How do I add new entities/businesses later?"**
Copy `example-entity/` to a new folder named with your two-letter entity code (e.g. `acme/` with file prefix `ac-`). Update the entity register in `entity-structure.md`.

**"Can my team use this?"**
Yes — but each person should have their own. Agents and context belong to individuals, not teams. Shared context (e.g. company values) lives in the company entity folder; personal context lives in the person's HQ.

**"What if Claude Code isn't following the rules in CLAUDE.md?"**
Read `CLAUDE.md` yourself. Rules need to be specific and unambiguous. If it's vague, the AI will guess. Tighten the rule.

---

## Next reads

- `CLAUDE.md` — the file Claude Code auto-loads. Understand it.
- `conventions.md` — the rules of the road (naming, frontmatter, SSOT).
- `master-context.md` — once filled in, the most important file in the system.
- `agents/README.md` — when you're ready to give your AI distinct roles.
- `harnesses/README.md` — when you're connecting more than one AI tool.
