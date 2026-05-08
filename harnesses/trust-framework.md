---
title: "Trust Framework"
entity: shared
type: harness-guide
tags: [trust, permissions, safety]
updated: 2026-Jan-15
---

# Trust Framework

> Defines what each AI harness is allowed to do. The single source of truth for "what can the AI do without asking?"
>
> Edit this carefully. The defaults below err toward conservative — relax them as you build trust with each harness.

---

## Trust Levels

Five levels, conservative to autonomous:

| Level | Name | Description |
|-------|------|-------------|
| 0 | **Read-only** | AI can read HQ. No writes anywhere. |
| 1 | **HQ writes** | AI can write to HQ markdown. No external systems. |
| 2 | **Drafts** | Level 1 + AI can write drafts to `~/Owner's Inbox/`. No sending/posting. |
| 3 | **Operational** | Level 2 + AI can act on external systems WITHIN named whitelists (e.g. add to calendar, file emails). Still no sending external comms. |
| 4 | **Send-with-approval** | Level 3 + AI can send/post on user's behalf, but only after explicit per-action confirmation. |
| 5 | **Autonomous-in-scope** | Level 4 + AI can act on a defined, narrow scope without per-action confirmation (e.g. "schedule meetings between 9am-3pm Tue/Wed/Thu"). Use sparingly. |

---

## Per-Harness Levels

Set the trust level for each harness here. Defaults shown — customise.

| Harness | Default level | Notes |
|---------|---------------|-------|
| **Claude Code** | 2 (Drafts) | High capability + file access = needs guardrails. Good default for daily work. |
| **Claude / ChatGPT chat** | 1 (HQ writes) | Less integrated. Mostly used for thinking, not action. |
| **Mobile / voice** | 0 (Read-only) | Can answer questions, can't change state. |
| **Automation runner** | 3 (Operational) | Scheduled tasks within a defined scope (e.g. cron jobs). |
| **Custom member-facing app** | varies | Set per-feature. |

---

## Universal Restrictions (All Harnesses, All Levels)

These apply regardless of trust level. They're hard limits.

- **Never delete files.** Move to `~/History/RedTag/`.
- **Never store credentials in markdown.**
- **Never execute financial transactions** (transfers, payments, invoices sent to clients).
- **Never modify the SSOT assignments** in `conventions.md` without user approval.
- **Never act on a request that contradicts `master-context.md` approval rules** without explicit user override per action.
- **Never make irreversible changes to external systems** (drop database tables, force-push, delete repos, etc.) without per-action confirmation.

---

## Per-Capability Whitelists

For Level 3 harnesses, define narrow whitelists of what they can do without asking. Examples:

### Calendar

- ✅ Read calendar.
- ✅ Add an event the user has explicitly described.
- ❌ Delete or modify existing events.
- ❌ Add events without the user explicitly asking.

### Email

- ✅ Read inbox (if granted).
- ✅ Apply labels.
- ✅ Save drafts (in the email client's draft folder OR `~/Owner's Inbox/`).
- ❌ Send any email.
- ❌ Delete any email (move to archive only).

### Files

- ✅ Read files in HQ.
- ✅ Write to HQ (with frontmatter).
- ✅ Read from `~/Inbox/`.
- ✅ Write to `~/Owner's Inbox/`.
- ✅ Move files to `~/History/Archives/` when explicitly processing.
- ❌ Move files to `~/History/RedTag/` without confirmation (this is "soft delete").
- ❌ Modify files in shared external storage (Drive, Dropbox) without confirmation.

### Code (if Claude Code is operating on a code repo)

- ✅ Read, propose edits, run tests.
- ✅ Commit to local branches.
- ❌ Push to remote.
- ❌ Force-push, ever.
- ❌ Modify CI/CD configs without per-action confirmation.

### Money

- ✅ Read financial records (for analysis).
- ✅ Generate invoice drafts.
- ❌ Send invoices.
- ❌ Make any transfer or payment.
- ❌ Modify financial records in the source system.

---

## Escalation Rules

If an AI is asked to do something outside its trust level:

1. State clearly that the action exceeds its trust level.
2. Tell the user what level would be needed.
3. Offer to do the closest safe action instead (e.g. "I can save this as a draft for you to send" instead of "I sent the email").
4. Never silently downgrade or work around the rule.

---

## Granting Higher Trust Temporarily

The user can authorise a higher trust level for a specific action:

> "Just for this conversation, you can [action]. I'll confirm before each one."

This grants the elevated level **for this session only**. It does not persist. It does not update this file. The user must re-grant in future sessions.

If the user wants a permanent change, they edit this file.

---

## When to Lower Trust

If an AI takes an action that turned out to be wrong, harmful, or unwanted:

1. Document what happened and why.
2. Lower the harness's trust level for that capability.
3. Add a more specific rule to this file or `master-context.md`.

Trust is built and lost in increments. Don't keep an AI at a level it's misused.

---

## Why This File Matters

Without an explicit trust framework, two failure modes happen:

- **Too restrictive:** the AI bothers the user with permission requests for trivial things.
- **Too permissive:** the AI takes unilateral actions the user didn't want.

Defining trust per harness, per capability, with explicit defaults, kills both.
