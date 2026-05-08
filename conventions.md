---
title: "Conventions"
entity: shared
type: reference
tags: [conventions, naming, ssot, frontmatter]
updated: 2026-Jan-15
---

# Conventions

The rules of the road. If you're an AI working in this repo, follow these. If you're the human, customise them once early on and then leave them alone.

---

## Universal Frontmatter

Every markdown file starts with this block:

```yaml
---
title: "Human-readable title"
entity: shared                # or your entity code
type: playbook                # see types below
tags: [tag1, tag2]
updated: 2026-Jan-15           # YYYY-Mon-DD format
---
```

**Required fields:** `title`, `entity`, `type`, `tags`, `updated`.

**Optional fields:**
- `owner` — name of the person responsible.
- `status` — `active` | `draft` | `archived`.
- `visibility` — `internal` | `published` | `member-facing`.
- `related` — list of related filenames without `.md`.

**Allowed `type` values:**
- `agent` — an AI agent's system prompt.
- `playbook` — a how-to guide for recurring work.
- `entity-brief` — the canonical reference doc for an entity.
- `framework` — a reusable structure or pattern (sales script, copy template, decision framework).
- `template` — a fillable template.
- `reference` — supporting reference material.
- `harness-guide` — describes how an AI tool connects to this KB.
- `journal` — a journal entry.
- `research` — a research brief.
- `person` — a relationship CRM file.

---

## Naming Conventions

### Dates

Always `YYYY-Mon-DD` with three-letter month abbreviation. No ambiguity.

- ✅ `2026-Jan-15`, `2026-Apr-20`, `2026-Dec-03`
- ❌ `2026-01-15`, `15/01/2026`, `Jan 15 2026`

### Files

| Type | Pattern | Example |
|------|---------|---------|
| Entity brief | `[code]-entity.md` | `ac-entity.md` |
| Playbook | `[code]-[topic]-playbook.md` | `ac-onboarding-playbook.md` |
| Framework | `[code]-[name].md` | `ac-sales-script.md` |
| Agent | `[role]-[persona].md` | `orchestrator-atlas.md` |
| Person | `[firstname]-[lastname].md` | `jane-smith.md` |
| Journal | `YYYY-Mon-DD.md` | `2026-Jan-15.md` |
| Research | `YYYY-Mon-DD_[topic-slug].md` | `2026-Jan-15_market-sizing.md` |
| Template | `[name]-template.md` | `proposal-template.md` |
| Dated file | `YYYY-Mon-DD_[entity]_[description]_v[X].[X].[ext]` | `2026-Jan-15_ac_quarterly-review_v1.0.pdf` |

### General rules

- Lowercase kebab-case for everything except dates and frontmatter values.
- No spaces in filenames. No special characters except `-` and `_`.
- Date prefix only on time-sensitive files (journals, research, dated deliverables). Not on stable reference (entity briefs, playbooks).
- Entity prefix prevents collisions across entities. Don't write `sales.md`; write `ac-sales-playbook.md`.

---

## Entity Codes

Each of your entities/businesses/brands gets a two-letter code. Define these once in `entity-structure.md`. Every file in that entity's folder uses the prefix.

Special: `shared` — for cross-entity files (conventions, glossary, this file).

---

## SSOT — Single Source of Truth

The most important rule. Each piece of information has **exactly one home**. Other places might point to it, but only one place is authoritative.

Customise the table in `CLAUDE.md` to match your tools. Some common splits:

| Information | Typical SSOT |
|-------------|--------------|
| Agent prompts, playbooks, voice, entity context | This repo |
| Contact identity (name, email, phone, company) | A contacts system (Google Contacts, Notion, Apple Contacts) |
| Contact intelligence (history, sentiment, summaries) | A database, or `people/` files in this repo |
| Calendar | Your calendar tool |
| Tasks | Your task tool (or `tasks.md` if you keep it simple) |
| Financial records | Your accounting tool |
| Code | Your code repo |
| Files / deliverables | Your file storage (Drive, Dropbox, iCloud) |
| Brand assets | Your design tool (Canva, Figma) |

**Rules:**
1. **Never duplicate.** If a fact lives in two SSOTs, drift is inevitable. Pick one.
2. **Pointers, not copies.** If you reference something stored elsewhere, link to it; don't copy it here.
3. **Override decisions are documented.** If you change an SSOT assignment, write it down in this file with the date and reason.

---

## Folder Boundaries

Folders are scoping mechanisms. Keep them honest.

- An entity folder contains only that entity's content. Cross-entity material lives at the root or in `shared/`.
- Agents can serve multiple entities (one Orchestrator who knows all your businesses) but agent files live in `agents/`, not in entity folders.
- Reusable patterns (templates, frameworks for general use) live at the root in `templates/` or `wisdom/`.

---

## Inboxes (External to HQ)

Two folders live alongside HQ, not inside it:

| Folder | Purpose | Direction |
|--------|---------|-----------|
| `~/Inbox/` | Files for AI to process | User → AI |
| `~/Owner's Inbox/` | Drafts and deliverables for review | AI → User |

The user drops things into `~/Inbox/`. AI reads, routes, files, then moves the original to `~/History/Archives/`.

AI puts deliverables (drafts, briefs, proposals) into `~/Owner's Inbox/`. The user reviews and either actions them or hands them back with explicit instructions.

**AI never sends, posts, or commits anything from `~/Owner's Inbox/` autonomously.** That's the user's gate.

---

## History (Soft Delete)

`~/History/RedTag/` is the soft-delete location. AI never deletes files from this repo or anywhere else; it moves them to RedTag. If the user confirms after 90 days that something isn't needed, then it can be hard-deleted.

Other History subfolders (Archives, Backups, Desktop, Downloads, Screenshots) are user-defined and can be customised.

---

## When in Doubt

1. Check this file.
2. Check `CLAUDE.md` for the lookup table.
3. Ask the user before making an irreversible change.
4. Default to the safer option.
