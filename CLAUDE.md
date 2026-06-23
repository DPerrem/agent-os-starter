> ⚠️ **PUBLIC REPOSITORY — sanitized template only.**
> This repo (`DPerrem/agent-os-starter`) is **public**. It is a shareable scaffold of the Agent OS structure, NOT a working knowledge base.
>
> **Never commit real Perrem business data, credentials, or infrastructure here** — no Supabase project refs / org slugs, no internal dashboard URLs, no deploy config, no client/financial info, no secrets. Anything real and durable belongs in the **private** `DPerrem/HQ` repo. Use only placeholders / `[xx]` examples in this repo. If a task needs real data, switch to the private repo first.

# CLAUDE.md — Project Instructions

> Auto-loaded by Claude Code at session start. This is the most privileged context slot in the system. Keep it stable. Working memory lives in `CURRENT.md`.

This is your personal Agent OS HQ. If you're Claude Code, read this in full before taking any action.

---

## What This Repo Is

A markdown knowledge base describing one person's work, life, and the entities they run. The AI's job is to read this context, act within the rules, and write back into it as it learns more.

Three layers:
- **Knowledge** (this repo, markdown) — stable, hand-curated.
- **Capability** (skills, scripts, MCPs) — lives elsewhere, called as needed.
- **Data** (databases, files, calendars, contacts) — the live transactional layer.

This repo is layer 1.

---

## Folder Map

```
HQ/
├── README.md
├── CLAUDE.md                  # This file
├── CURRENT.md                 # Working memory — read for any current-state task
├── master-context.md          # Who I am, voice, approval rules
├── conventions.md             # Naming rules, SSOT map, frontmatter spec
├── entity-structure.md        # My businesses/brands/trusts/projects
├── glossary.md                # Shorthand and acronyms
├── tasks.md                   # Open work items
│
├── agents/                    # Role-specific AI agents
├── harnesses/                 # How AI tools connect to this KB
├── people/                    # Relationship CRM
├── templates/                 # Reusable templates
├── journal/                   # Daily journal (markdown)
├── research/                  # Research briefs
├── wisdom/                    # Continual-learning layer (books, voices, principles)
│
└── [entity-folders]/          # One per entity (see entity-structure.md)
    ├── [code]-entity.md
    ├── playbooks/
    └── frameworks/
```

---

## Two External Folders You Should Know About

These live **next to** HQ, not inside it:

- **`~/Inbox/`** — drop zone TO me from the user. Files for AI to process: receipts, PDFs, voice memos, screenshots, scribbled notes. When the user asks "process my inbox" or "what's in my inbox," check this folder, route content to the right place in HQ, then move the original to `~/History/Archives/`.
- **`~/Owner's Inbox/`** — delivery zone FROM me to the user. AI deliverables awaiting review: draft emails, briefs, summaries, proposals. **AI never sends, posts, or commits anything from this folder. The user is the gatekeeper.**

When AI produces something for the user to review, it goes in `~/Owner's Inbox/`. When AI takes action on something the user has dropped, it comes from `~/Inbox/`.

Also relevant:
- **`~/History/RedTag/`** — the "soft delete" location. AI never deletes files. It moves them here.
- **`~/History/Archives/`** — long-term storage of processed material.

---

## Universal Frontmatter

**Every markdown file in this repo starts with frontmatter.** No exceptions.

```yaml
---
title: "Human-readable title"
entity: shared                # or your entity code (see entity-structure.md)
type: playbook                # agent | playbook | entity-brief | template | reference | harness-guide
tags: [sales, onboarding]     # free-form
updated: 2026-Jan-15           # YYYY-Mon-DD
---
```

Optional fields when relevant: `owner`, `status` (active|draft|archived), `visibility` (internal|published), `related` (list of filenames without `.md`).

If you're creating a new file, you MUST include this frontmatter. If you're editing one, preserve it and bump `updated:` to today's date.

---

## Lookup Rules — Where to Find Things

| If you need… | Look in |
|--------------|---------|
| Who I am, voice, approval rules | `master-context.md` |
| Current focus / this week / open questions | `CURRENT.md` |
| Open work items / backlog | `tasks.md` |
| Naming, SSOT, frontmatter rules | `conventions.md` |
| My shorthand / acronyms | `glossary.md` |
| List of my entities/businesses/brands | `entity-structure.md` |
| An agent's system prompt | `agents/[role]-[persona].md` |
| How a specific AI tool connects to this KB | `harnesses/[harness-name].md` |
| What an AI is allowed to do | `harnesses/trust-framework.md` |
| Entity-specific context (offer, voice, services) | `[entity]/[code]-entity.md` |
| Entity-specific playbook (sales, onboarding, etc.) | `[entity]/playbooks/[code]-[topic]-playbook.md` |
| Entity-specific framework / template / script | `[entity]/frameworks/[code]-[name].md` |
| A person's relationship intelligence | `people/[firstname-lastname].md` |
| Reusable templates (proposal, meeting notes) | `templates/[name]-template.md` |
| Today's journal entry | `journal/YYYY-Mon-DD.md` |
| A research brief | `research/YYYY-Mon-DD_[topic].md` |
| Distilled principles from books/voices | `wisdom/sources/`, `wisdom/voices/`, `wisdom/principles/` |

---

## When to Read CURRENT.md

Read it when the task is about current state — priorities, this-week work, open questions, recent decisions.

Skip it when the task is referential — writing a playbook, drafting a proposal, looking up a rule. Those only need stable files.

---

## What Lives Where (SSOT — Single Source of Truth)

Define your own SSOT map in `conventions.md`. The starter template includes:

| Data | Home |
|------|------|
| Agent prompts, playbooks, entity knowledge | This repo |
| Contact identity (name, email, phone) | [Your contact system — Google Contacts, Notion, etc.] |
| Tasks | [Your task system — ClickUp, Linear, Things, plain markdown] |
| Calendar | [Your calendar system] |
| Financial records | [Your accounting system] |
| Files / deliverables | [Your file storage] |
| Code | [Your code repo location] |
| Brand assets | [Your design tool] |

**Never duplicate content between two SSOTs.** If the truth lives in the calendar, don't also keep it here. Keep a *pointer* if needed, not a copy.

---

## What You Can and Can't Do in Here

### You can
- Read any file in this repo.
- Propose new files (always with frontmatter).
- Update existing files (preserve frontmatter, bump `updated:`).
- Move files (with the user's confirmation).
- Run skills the user has installed.
- Save things to `~/Owner's Inbox/` for the user to review.
- Read files from `~/Inbox/` and route them appropriately.

### You should NOT
- Edit agent files outside the role you've been assigned.
- Edit entity files outside your scope.
- Create files without frontmatter.
- Use generic filenames that collide across entities (e.g., `sales.md` without an entity prefix).
- Store secrets or credentials in markdown.

### You MUST NOT (these are universal)
- Send emails, post to social, or publish anything publicly without explicit per-action approval.
- Move money or execute financial transactions.
- Delete files. Move them to `~/History/RedTag/` instead.
- Modify the SSOT assignments in `conventions.md` without the user's approval.
- Make irreversible changes to external systems (databases, repos, third-party tools) without asking.

The user adds further rules in `master-context.md`. Read those.

---

## Boot Sequence

1. This file (auto-loaded).
2. `master-context.md` — who the user is.
3. `CURRENT.md` — only if the task needs current state.
4. Task-specific files per the lookup table above.

---

## Naming Convention Reminder

- Dates: `YYYY-Mon-DD` (e.g. `2026-Jan-15`). Three-letter month, no ambiguity.
- Dated files: `YYYY-Mon-DD_description.ext`.
- Entity files: prefixed with the entity's two-letter code (e.g. `ac-entity.md`, `ac-onboarding-playbook.md`).
- Agent files: role first, persona suffix (e.g. `orchestrator-atlas.md`).
- Person files: `firstname-lastname.md`.

Full rules in `conventions.md`.

---

## If You're Confused

1. Re-read the lookup rules above.
2. Check `conventions.md` for filing rules.
3. If a file you expected isn't where you looked, ask the user.
4. Ask before making any irreversible change.

---

*This file changes rarely. Current-state notes go in `CURRENT.md`.*
