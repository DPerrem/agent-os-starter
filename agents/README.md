---
title: "Agents — Overview"
entity: shared
type: reference
tags: [agents, pattern]
updated: 2026-Jan-15
---

# Agents

> One file per AI agent role. Each file is a system prompt + scope + handoff rules. Agents are addressed by role + persona (e.g. "@Atlas" = the Orchestrator).

---

## The Pattern

An "agent" in this system is **a defined role with a name, a scope, a voice, and a set of rules.** It's a prompt template that you load to put the AI in that mode.

You give each agent two things:
- A **role** (what they do — Orchestrator, Sales Lead, Researcher).
- A **persona** (a name — Atlas, Robin, Maya). Personas make agents memorable and addressable. You don't have to use one, but it helps.

File naming: `[role]-[persona].md`. e.g. `orchestrator-atlas.md`, `research-maya.md`.

Every agent file follows the same structure. See `orchestrator-atlas.md` for the worked example.

---

## Common Roles

You don't need all of these. Most people start with 1-3 and grow into more. Use this list as a menu, not a checklist.

| Role | Purpose | Typical first agent? |
|------|---------|----------------------|
| **Orchestrator** | Top-level routing. Knows everything, delegates. The "chief of staff." | ✅ Often the first |
| **Admin / PA** | Diary, email triage, file routing, reminders | ✅ Often the first |
| **Communications** | Drafts emails, replies, messages in your voice | ✅ Often the first |
| **Content** | Long-form writing — blog, newsletter, social | |
| **Marketing** | Campaign planning, ads, funnels | |
| **Sales** | Pipeline, follow-ups, proposals | |
| **Research** | Briefs, market analysis, deep-dives | |
| **Finance** | Bookkeeping prep, invoice tracking, financial reviews | |
| **Fulfilment / Ops** | Project delivery, internal coordination | |
| **Coach / Mentor** | Asks questions, challenges your thinking | |

---

## How Agents Work Together

If you have multiple agents:

- **Orchestrator** is the front door. You talk to the Orchestrator; it delegates to specialists or runs work itself if simple.
- Specialists stay in their lane. Sales doesn't write blog posts. Content doesn't manage diary.
- All agents share the same **base context** (this whole HQ) but have different **scope and tone**.

You can implement this many ways:
- **Lightweight:** all agents are just prompt templates you paste at session start. Different "personas" within Claude Code.
- **Mid-weight:** agents are saved as Claude Code custom agents (`.claude/agents/`) and addressable via `@mention`.
- **Heavy:** each agent runs in its own harness (Claude Code, ChatGPT, custom assistant) with its own scope.

Pick what matches your situation. Most people stay lightweight for the first 3 months.

---

## Universal Agent Rules

Every agent inherits these rules from `master-context.md`:

- Read the user's voice rules. Match their tone.
- Honour the approval rules — never act on protected actions without explicit per-action approval.
- Save deliverables to `~/Owner's Inbox/` for review.
- Never delete; move to `~/History/RedTag/`.
- Never store credentials in markdown.

Per-agent files extend these with role-specific behaviour.

---

## When to Create a New Agent

Create a new agent file when:

- You catch yourself giving the same setup prompt 3+ times.
- A specific role has a distinct voice or scope from your default.
- You want to delegate a category of work consistently.

Don't create new agents just for variety. More agents = more context to maintain. Three good agents > nine half-built ones.

---

## Naming Personas

Some patterns that work:

- **Mythological** (Atlas, Iris, Hermes) — memorable, archetypal.
- **Names of mentors** — what would [your hero] do?
- **Job-title-as-name** (just call it "Operations" or "Ops Lead") — simplest, no anthropomorphism.
- **Nicknames you'd use for a real assistant** — Pat, Robin, Sam.

Pick what feels natural to talk to. You'll be addressing them dozens of times a week.
