# Agent OS Starter Kit

A working template for running your own personal Agent OS — a markdown-based knowledge base that AI agents (Claude Code, ChatGPT, custom assistants) can read, reason over, and write back into.

## What this is

This folder is a **scaffold**, not a finished system. It gives you:

- The folder structure for a personal HQ
- Templates for the core context documents an AI needs to be useful (who you are, what you're doing, who's in your orbit, what tone you write in)
- One worked example of each pattern (one agent file, one entity brief, one playbook, one wisdom source) so you can see the shape
- A naming convention and frontmatter spec so files stay findable as the system grows
- A getting-started prompt that tells Claude Code how to interview you and fill it all in

It is **not** a turnkey product. You will fill it in over the first 1-3 weeks of using it, and you will keep editing it forever as your work and life change. That's the point — this is your living context, not a one-time setup.

## What's the philosophy

Three layers, kept separate:

1. **Knowledge** (this folder) — markdown files describing who you are, what you do, how you work, and who's in your world. Stable, hand-curated, version-controlled.
2. **Capability** (skills, scripts, MCPs) — the *doing* layer. Lives elsewhere (your skills repo, MCP servers, Claude Code skills directory).
3. **Data** (databases, contacts, calendars, files) — the live transactional layer. Lives in real systems (Supabase, Google Contacts, your file storage).

This folder is layer 1 only. It tells the AI **what's true** so the AI can use layers 2 and 3 sensibly.

## Who this is for

Anyone serious about working with AI as a daily collaborator who has hit the ceiling of one-shot prompts and wants:
- An AI that knows who they are without being re-told every conversation
- A single source of truth for their voice, their goals, their people, their decisions
- A way to share context across multiple AI tools (Claude Code, ChatGPT, custom agents) without copy-pasting

If you've got <10 hours/week to invest in AI and you just want a chatbot, this is overkill. If you want AI to operate as part of your team, this is the foundation.

## How to use it

1. Read `GETTING-STARTED.md`.
2. Copy this whole folder to a new location (e.g. `~/HQ/`).
3. Open it in Claude Code (`cd ~/HQ && claude`).
4. Run the interview prompt in `GETTING-STARTED.md`.
5. Iterate weekly. Add files as patterns emerge.

## What's included

```
agent-os-starter/
├── README.md                  # This file
├── GETTING-STARTED.md         # Step-by-step setup + interview prompt
├── CLAUDE.md                  # Project instructions for Claude Code (template)
├── conventions.md             # Naming rules, SSOT map, frontmatter spec
├── master-context.md          # Who you are, voice, approval rules (template)
├── CURRENT.md                 # Working memory — current focus (template)
├── tasks.md                   # Open work items (template)
├── glossary.md                # Your shorthand (template)
├── entity-structure.md        # Your businesses/brands/projects (template)
│
├── agents/                    # One file per AI agent role
│   ├── README.md              # Pattern explanation + role catalogue
│   └── orchestrator-atlas.md  # Worked example
│
├── harnesses/                 # How AI tools connect to this KB
│   ├── README.md              # The 4-harness pattern
│   └── trust-framework.md     # What each AI is allowed to do (template)
│
├── example-entity/            # ONE example showing the entity pattern
│   ├── ex-entity.md           # Example entity brief
│   ├── playbooks/             # Example playbook
│   └── frameworks/            # Example framework
│
├── people/                    # Relationship CRM (one file per person)
│   └── _template.md
│
├── templates/                 # Reusable templates
│   ├── proposal-template.md
│   ├── meeting-notes-template.md
│   ├── decision-log-template.md
│   └── journal-entry-template.md
│
├── journal/                   # Daily journal (markdown)
│   └── 2026-Jan-15-example.md
│
├── research/                  # Research briefs from your AI research agent
│   └── 2026-Jan-15_example-topic.md
│
└── wisdom/                    # Continual-learning layer (books, voices, principles)
    ├── README.md
    ├── index.md
    ├── sources/
    ├── voices/
    └── principles/
```

## What's NOT included

By design, this kit excludes:

- Your specific entity briefs, playbooks, and frameworks (you'll build these)
- Your specific people, journal, and research files (you'll build these)
- A skills/capability layer (use the Claude Code skill marketplace, or build your own private skills repo and clone it into `skills/`)
- A database layer (you can connect Supabase, Notion, or whatever fits — see `harnesses/trust-framework.md`)
- Specific approval rules or financial guardrails (templated, not prescribed — you decide)

## License

Use this freely for personal or commercial work. If you build something cool with it, tell us.

## Credit

Distilled from Luke Davies' personal Agent OS (HQ), built across 2024-2026 running multiple businesses with AI as core staff.
