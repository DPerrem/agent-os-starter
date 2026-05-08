---
name: digital-filing
description: A folder-and-naming methodology for personal and business file organisation. Uses the PATH framework (Projects, Areas, Tools, History) and the PKA philosophy (Personal Knowledge Assistance — folders + AI as the entire knowledge management system, no PKM apps). Use this skill when the user wants to organise files, name folders, clean up their desktop or downloads, set up a new project folder, audit their filing system, archive completed work, set up a single-source-of-truth map for their tools, or asks about PATH, PKA, filing methodology, two-inbox pattern, or "where should this go." The skill teaches the methodology and applies it to any new or existing folder structure.
---

# Digital Filing — PATH + PKA Methodology

A complete digital filing system. Originally developed for multi-entity small business, but works for any personal or professional setup. The two big ideas:

- **PATH** is the folder structure — Projects, Areas, Tools, History.
- **PKA** is the philosophy — your folders + AI ARE your knowledge management system. No Notion. No Obsidian. No app-of-the-month.

---

## PKA Philosophy (Personal Knowledge Assistance)

The era of trying every PKM app is over. The pattern that wins:

- **The folder IS the system.** A clean folder structure on your computer + AI access = your entire KM system. No external tool required.
- **Tool-agnostic.** The AI brain is swappable — Claude today, something else tomorrow. Your data stays yours because it's just files and folders.
- **Three layers, no more:**
  1. **Knowledge** — markdown in your HQ folder.
  2. **Capability** — skills, scripts, MCPs.
  3. **Data** — databases, contacts, calendars.
  Nothing belongs in two places.
- **Agents are the filing interface.** You stop filing manually. You say "I just finished this" or "I got this in" — the AI handles placement, naming, and indexing.
- **Two-inbox pattern.** One drop zone for things going TO the AI, one for things coming FROM the AI for your review.

---

## The 8 Core Rules

These govern every filing decision. Don't break them.

### 1. Single Source of Truth (SSOT)

Every piece of information lives in **exactly one** definitive place. Other places might link to it. Only one is authoritative.

This doesn't mean everything goes in one app. It means absolute clarity about where each thing lives. When you go to that place, you know with certainty it's the most up-to-date version.

**Common SSOT splits:**

| Information | Lives in |
|-------------|----------|
| Working documents (drafts, in-progress) | Cloud drive (Drive, Dropbox, iCloud) |
| Finalised documents (PDFs, signed) | Project folder + project management tool |
| Financial records | Accounting tool (Xero, QuickBooks) |
| Code | Git repo |
| Contact identity (name, email, phone) | Contacts tool |
| Tasks | Task tool (or `tasks.md` in HQ if you keep it simple) |
| Calendar events | Calendar tool |
| Brand assets | Design tool (Canva, Figma) |
| Long-form notes / playbooks / personal context | HQ folder (markdown) |

Customise this list to your tools. The point is: **decide once, document the decision, never duplicate.**

### 2. Three-Click Rule

Any file should be reachable in maximum 3 clicks from your root. If it takes more than 3 clicks, the structure is too deep. Restructure.

### 3. Maximum 20 Subfolders

No single folder should have more than ~20 subfolders. More than that creates clutter and slows scanning. If you exceed 20, split into subcategories.

### 4. Centralised Storage

For business files, everything lives in shared cloud storage owned by the business. Not on personal devices. Not in personal cloud accounts. Not as email attachments.

For personal files, pick **one** primary location and stick to it. Don't fragment across iCloud, Dropbox, and Drive.

### 5. Group-Based Access (for teams)

Set permissions through groups (Executive, Project Management, All Team, Contractors). Never share individual files one-by-one. It's unmanageable as the team grows.

### 6. Consistent Naming Conventions

Standardised naming everywhere. If different people call the same thing different names, files become unfindable.

See "Naming Conventions" below for the canonical patterns.

### 7. Prioritise Frequently Used

Most-accessed folders at the top. Use numeric prefixes (`01_`, `02_`, `03_`) to push important folders above alphabetical defaults.

### 8. Less Friction the Better

Minimise effort between receiving/creating a file and filing it. Set up automations where possible (auto-filing email attachments, auto-routing receipts to accounting). The easier filing is, the more consistently it gets done.

---

## PATH Folder Structure

PATH = **P**rojects, **A**reas, **T**ools, **H**istory. These are the four root folders inside any major space (your shared drive, your personal cloud, etc.).

```
PATH/
├── Projects/    # Short-term, goal-oriented work with clear deadlines
├── Areas/       # Ongoing responsibilities and operational zones
├── Tools/       # Reusable resources, assets, knowledge
└── History/     # Completed work, archives, soft-deleted items, backups
```

### Projects/

**Definition:** Short-term, goal-oriented work with clear deadlines and deliverables.

**Test:** Does it have a finish line and a deliverable? → Project.

**Structure:**

```
Projects/
├── Active/
│   └── [Project Name]/      # One folder per active project
│       ├── 01_Brief/
│       ├── 02_Working/
│       ├── 03_Final/
│       ├── 04_Comms/
│       └── 05_Archive/
└── Completed/               # Move whole project folder here when done
    └── [Project Name]/
```

**Project naming pattern:** `[YYMM]_[short-name]` — e.g. `2601_website-rebuild`, `2602_q1-launch`. Date prefix gives natural chronological sorting.

**Project lifecycle:** When a project completes, move the entire folder from `Active/` to `Completed/`. Don't leave dead projects in Active — they obscure what's live.

### Areas/

**Definition:** Ongoing responsibilities and operational zones. They never "complete" like a project does.

**Test:** Do you always manage this, with no finish line? → Area.

**Common Areas:**
- Sales & Lead Management
- Marketing
- Content
- Finance & Accounting
- People / Team / HR
- Legal
- Insurance
- Compliance & Quality
- Reporting & Analytics
- Travel
- Properties (if relevant)

Each Area has its own subfolder structure. Keep it shallow — the goal is fast retrieval, not categorisation completeness.

### Tools/

**Definition:** Reusable resources, assets, and knowledge that support your work. Not tied to a specific project.

**Test:** Will you use this again and again across multiple projects? → Tool.

**Common Tools subfolders:**
- How-To Guides & SOPs
- Templates
- Forms & Checklists
- Branding & Marketing assets
- Media library (logos, photos, video)
- Best Practices & Learning
- Databases & Trackers

If a thing is specific to one project, it belongs in that project's folder. If it's reusable, it's a Tool.

### History/

**Definition:** Completed projects, archived documents, soft-deleted items, backups. Nothing is ever truly deleted — it goes to History.

```
History/
├── Archives/    # Completed projects and old documents
├── RedTag/      # Uncertain, unused, or potentially-duplicate items awaiting sorting
└── Backups/     # Secure copies of critical data
```

**RedTag definition:** Any file that's not actively used, hasn't been touched in 6+ months, might be a duplicate, or you're unsure where it belongs. Move it to RedTag immediately. Sort it later during dedicated cleanup time.

**The non-negotiable rule:** AI never deletes files. It moves them to RedTag. Hard delete only happens after you confirm — typically 90 days later if nothing in RedTag has been retrieved.

---

## The Two-Inbox Pattern

Two folders that live alongside your HQ, **not inside it**:

### `~/Inbox/` — User → AI

The drop zone for anything you want AI to process:
- Photos of receipts and invoices
- PDFs to summarise
- Voice memos to transcribe
- Screenshots of conversations
- Notes you scribbled and want filed
- Files a colleague sent you that need triage

Standing AI instruction: when the user asks to "process my inbox" or "what's in my inbox," check this folder, route content to the right PATH location, then move the original to `History/Archives/`.

### `~/Owner's Inbox/` — AI → User

The delivery zone for AI deliverables awaiting human review:
- Draft emails
- Briefs and summaries
- Research outputs
- Proposals
- Anything flagged for the user's decision

**The rule: AI never sends, posts, or commits anything from this folder.** The user is the gatekeeper. You review, edit, approve, then either action it yourself or hand it back to the AI with explicit "send this" instructions.

This separation kills two failure modes:
- Without `Owner's Inbox/`, AI bothers the user with permission requests for every draft.
- Without the gatekeeping rule, AI starts acting unilaterally on drafts.

---

## Naming Conventions

### Dates

Always `YYYY-Mon-DD` with three-letter month abbreviation. No ambiguity.

- ✅ `2026-Jan-15`, `2026-Apr-20`, `2026-Dec-03`
- ❌ `2026-01-15`, `15/01/2026`, `Jan 15 2026`

### Files

| Type | Pattern | Example |
|------|---------|---------|
| Dated working file | `YYYY-Mon-DD_[description]_v[X].[X].[ext]` | `2026-Jan-15_proposal_v1.0.docx` |
| Project folder | `[YYMM]_[short-name]` | `2601_website-rebuild` |
| Receipt / invoice | `YYYY-Mon-DD_[supplier]_[$amount].[ext]` | `2026-Jan-15_acme_$340.pdf` |
| Photo / scan | `YYYY-Mon-DD_[subject]_[N].[ext]` | `2026-Jan-15_office-floorplan_1.jpg` |
| Markdown reference | `[topic-slug].md` (kebab-case) | `weekly-review-playbook.md` |

### General rules

- Lowercase kebab-case for everything except dates and proper names.
- No spaces in filenames. Use `-` (kebab-case) or `_` (snake-case) only.
- No special characters other than `-` and `_`.
- Date prefix only on time-sensitive files. Stable reference (playbooks, SOPs) doesn't need dates in the name.
- Version numbers (`v1.0`, `v1.1`) only for working drafts. Final files drop the version.

---

## Universal Frontmatter (for HQ markdown)

Every markdown file in your HQ starts with this block:

```yaml
---
title: "Human-readable title"
entity: shared                # or your entity code
type: playbook                # see types below
tags: [sales, onboarding]     # free-form
updated: 2026-Jan-15           # YYYY-Mon-DD
---
```

**Required:** `title`, `entity`, `type`, `tags`, `updated`.

**Allowed `type` values:** `agent`, `playbook`, `entity-brief`, `framework`, `template`, `reference`, `harness-guide`, `journal`, `research`, `person`.

If you create a markdown file in HQ without frontmatter, the file is malformed. Add it.

---

## Routing Rules (When the AI Is Filing)

When the AI receives a file (from the user dropping in `~/Inbox/`, from email, from a task hand-off), it asks these questions in order:

1. **Is this for one specific project?** → Route to that project folder under `Projects/Active/[Project Name]/[appropriate subfolder]/`.
2. **Is this an ongoing operational area?** → Route to the relevant `Areas/[Area Name]/` subfolder.
3. **Is this reusable across multiple projects?** → Route to the appropriate `Tools/` subfolder.
4. **Is this completed, archived, or unclear?** → Route to `History/`. If unclear, RedTag.
5. **Is this narrative/reference content the AI should know about?** → Route to HQ as markdown with frontmatter.

If unsure, drop it in `~/Owner's Inbox/` with a note explaining the ambiguity. Don't guess.

---

## Sensitive / Personal Data

When AI is filing, it must NEVER:

- Mix personal files into business folders.
- Mix HR / financial / wages data into general team-accessible folders.
- File confidential client information in publicly-accessible Tools folders.
- Store passwords, API keys, or secrets in markdown anywhere.

If a file's classification is ambiguous (could be personal or business, could be confidential or general), it goes to `~/Owner's Inbox/` with a flag asking the user to clarify.

---

## Weekly / Periodic Maintenance

Run these on a cadence (weekly minimum, monthly minimum for the bigger ones).

### Weekly: Desktop & Downloads sweep
- Move everything off the desktop.
- Process the Downloads folder: file what's needed, move the rest to `History/Archives/Downloads/`.
- Clear screenshots into the relevant project or `History/Archives/Screenshots/`.

### Weekly: Inbox sweep
- Process anything still in `~/Inbox/` and `~/Owner's Inbox/`.
- Anything in `~/Owner's Inbox/` for >7 days without action → move to RedTag and add a task to revisit.

### Monthly: RedTag review
- Open `History/RedTag/`.
- For each item: confirm what it is, route to the right place, or hard-delete if it's been there 90+ days unused.

### Quarterly: PATH structure audit
- Walk through Projects, Areas, Tools, History.
- Anything completed and not moved? Move it.
- Anything in Active that hasn't been touched in 60 days? Probably dead — move to RedTag or Completed.
- Any Area or Tool subfolder with >20 items? Split it.

---

## Setting Up From Scratch

If the user is starting fresh, follow this sequence:

1. Create `~/HQ/` (the markdown knowledge base).
2. Create `~/Inbox/` and `~/Owner's Inbox/` (the two-inbox pattern).
3. Create `~/History/` with `Archives/`, `RedTag/`, `Backups/` subfolders.
4. In their primary cloud drive, create `PATH/` with `Projects/`, `Areas/`, `Tools/`, `History/`.
5. Inside `Projects/`, create `Active/` and `Completed/`.
6. Customise Areas based on what they actually run (don't pre-create empty folders for things they don't do).
7. Set up the SSOT map in their HQ's `conventions.md`.

Don't pre-build empty Tools and Areas subfolders for things they don't yet have content for. Build the structure as needed.

---

## When the User Resists Filing

People resist filing for two reasons: friction (it takes too long) and ambiguity (where does this go?).

PATH solves the second. The two-inbox pattern + AI-as-filing-interface solves the first.

If a user says "I'll never keep up with this":
- Don't ask them to file. Ask them to drop into `~/Inbox/`.
- AI files on their behalf. They confirm via review.
- The whole point of PKA is that **humans no longer file manually**.

---

## When to Use This Skill

Use this skill when:

- The user asks to organise files, set up a folder structure, or clean up their digital workspace.
- The user mentions PATH, PKA, filing methodology, or "where should this go."
- The user asks about the two-inbox pattern, RedTag, or SSOT.
- The user is starting a new business, project, or HQ and needs a folder structure.
- The user asks for naming conventions, date formats, or frontmatter rules.
- The user wants to audit their existing structure for problems.

Do NOT use this skill for:

- Project management within a folder (that's a separate concern).
- Code organisation (use language-specific conventions).
- Database schema design (different domain entirely).

---

## Credit

Distilled from Luke Davies' personal Agent OS, originally built for multi-entity construction and AI consulting businesses. The PATH framework draws from Tiago Forte's PARA method, adapted for AI-first operation.
