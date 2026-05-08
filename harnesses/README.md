---
title: "Harnesses — Overview"
entity: shared
type: reference
tags: [harnesses, integration, infrastructure]
updated: 2026-Jan-15
---

# Harnesses

> A "harness" is the actual AI tool or runtime that connects to this knowledge base. Different harnesses have different strengths, different access levels, and different appropriate uses.

---

## What's a Harness?

This HQ is just markdown files. It can't *do* anything by itself. A harness is the AI tool you use to read, reason over, and write back into HQ.

Common harnesses:

| Harness | What it is | Best for |
|---------|------------|----------|
| **Claude Code** | CLI in your terminal | Heavy work, file manipulation, code, multi-step tasks |
| **ChatGPT / Claude desktop** | Chat-based desktop apps | Quick questions, writing on the go, conversational work |
| **Custom web app** | A bespoke front-end you build | Member-facing AI, branded experiences |
| **Voice assistant** | A voice harness (e.g. via API) | Hands-free use, driving, walking |
| **Automation runner** | n8n, Zapier, custom scripts | Scheduled tasks, integrations |

Each harness has different:
- **Tools available** (file system access, web search, code execution, MCP servers)
- **Memory model** (short context window, long context, persistent memory)
- **Trust level** (what you let it do unilaterally)
- **Cost model** (per-token, subscription, pay-per-use)

---

## Why Multiple Harnesses?

Because no single AI tool is best at everything.

- Claude Code is unbeatable for working with files and code.
- A chat app is faster for "I'm walking and want to think out loud."
- A voice harness is right for hands-free moments.
- A scheduled automation runner is right for "every Monday at 6am, do X."

The same HQ context flows through all of them. The user gets a consistent experience — same voice, same rules, same goals — across surfaces.

---

## How to Connect a Harness

The pattern is similar regardless of harness:

1. **Give it access** to the HQ folder (file system mount, sync, or API).
2. **Point it to `CLAUDE.md`** (or its equivalent loading mechanism) so it loads the project instructions.
3. **Define its scope** in a harness file here (e.g. `harnesses/claude-code.md`) — what it can read, what it can do, what it can't.
4. **Set its trust level** in `trust-framework.md`.

---

## Starter Harnesses

For most people getting started, **one harness is enough**: Claude Code in the terminal.

Add a second harness when:
- You hit a real friction point with the first (e.g. you want to chat from your phone).
- You have a specific use case the first can't serve (e.g. scheduled automation).
- You've maxed out value from the first (uncommon in the first 6 months).

Don't add harnesses to be impressive. Add them to remove friction.

---

## File Per Harness

When you formalise a harness, give it a file in this folder:

```
harnesses/
├── README.md             # This file
├── claude-code.md        # How Claude Code is configured for me
├── trust-framework.md    # What each harness is allowed to do
└── [other-harness].md    # Add as you adopt new tools
```

Each harness file describes:
- Its scope (what it can read / write)
- Its tools (skills, MCPs, APIs available)
- Its limits (what's deliberately blocked)
- Its trust level (cross-reference `trust-framework.md`)
- Setup notes (so you can rebuild it if needed)

---

## See Also

- `trust-framework.md` — the rules of what each harness can do.
- `agents/README.md` — agents are the *roles* that run inside harnesses.
