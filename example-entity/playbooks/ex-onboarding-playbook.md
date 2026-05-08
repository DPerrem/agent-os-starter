---
title: "Acme Co — Client Onboarding Playbook"
entity: ex
type: playbook
tags: [example, onboarding, playbook]
updated: 2026-Jan-15
status: active
---

# Acme Co — Client Onboarding Playbook

> ⚠️ WORKED EXAMPLE. Acme Co is fictional. Use this as the shape for your real playbooks.

---

## When This Runs

Triggered when a new client signs the engagement letter. Owned by the lead consultant. Typically takes 5 business days from signature to kickoff.

---

## Outcome

By the end of onboarding:
- Client has had a 60-min kickoff call with the lead consultant + their primary stakeholder.
- We have access to the systems we need (read-only at first).
- The client team knows who to contact, when, and how.
- Calendar is booked for the first 4 weeks of the engagement.
- Project folder exists in our file system, populated with the templates.

---

## Steps

### Step 1 — Signed contract received (Day 0)

**Owner:** Operations.
- File the signed PDF in the client folder.
- Send the welcome email (template: `~/HQ/example-entity/frameworks/ex-welcome-email.md` — not included in starter).
- Add the client to the CRM with stage = "Onboarding".
- Send invoice for the first milestone payment (50% deposit per contract).

**AI can:** draft the welcome email, draft the invoice in the accounting system. ❌ **AI cannot:** send the email or send the invoice — both go to `~/Owner's Inbox/`.

### Step 2 — Kickoff scheduling (Day 1-2)

**Owner:** Lead consultant.
- Reply to the welcome email confirming receipt.
- Propose 3 kickoff slots in the next 5 business days.
- Once confirmed, send calendar invite with agenda attached.

**AI can:** propose the slots based on calendar availability, draft the invite. Save draft to `~/Owner's Inbox/`.

### Step 3 — Pre-kickoff prep (Day 3-4)

**Owner:** Lead consultant.
- Read everything we have on the client (intake form, sales notes, website).
- Draft a 1-page brief: who they are, what they think the problem is, what we suspect, what to validate in kickoff.
- Confirm system access we'll need.

**AI can:** synthesise the intake brief from sales notes + website. Save to `~/Owner's Inbox/`.

### Step 4 — Kickoff call (Day 5)

**Owner:** Lead consultant.
- Run the standard kickoff agenda:
  1. Re-confirm scope and outcomes.
  2. Walk through the 6-week timeline.
  3. Identify the 5-7 people we'll need to interview.
  4. Confirm communication cadence (default: weekly Monday update).
  5. Open Q&A.
- Take recorded notes (transcription tool).
- End with explicit next steps + named owners.

**AI can:** generate the post-call summary from the transcript, draft the follow-up email. Save to `~/Owner's Inbox/`.

### Step 5 — Post-kickoff (Day 5-6)

**Owner:** Lead consultant.
- Send follow-up email with: meeting summary, action items, week-1 calendar.
- Update CRM stage to "Engagement Active".
- Create the project folder structure (template).
- Add weekly status meetings to calendar for the engagement duration.

**AI can:** create the folder structure, draft the follow-up. ❌ **AI cannot:** send the follow-up unilaterally.

---

## Templates Used

- Welcome email — `frameworks/ex-welcome-email.md` (not included in starter)
- Kickoff agenda — `frameworks/ex-kickoff-agenda.md` (not included in starter)
- Intake brief format — `frameworks/ex-intake-brief.md` (not included in starter)
- Post-call summary — `templates/meeting-notes-template.md` at HQ root

---

## Standard Times

- Total active time, lead consultant: ~3 hours.
- Total active time, ops: ~30 mins.
- Calendar elapsed: 5 business days.

---

## Common Issues

- **Client is slow to confirm kickoff time** — Day 3 chase, Day 5 escalate to phone.
- **Client doesn't fill in intake form** — Don't proceed without it. Push back.
- **Stakeholder added late** — Re-confirm scope. Don't assume new stakeholder agrees with the original brief.

---

## When to Update This Playbook

- After every 3rd onboarding, run a retro and update what changed.
- Whenever a client gives feedback that maps to a step here.
- When tooling changes (e.g. new CRM).
