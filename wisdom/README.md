---
title: "Wisdom — Overview"
entity: shared
type: reference
tags: [wisdom, learning, principles]
updated: 2026-Jan-15
---

# Wisdom

> A continual-learning layer. Distilled principles from books, podcasts, courses, mentors, and people whose work you want to learn from.
>
> The point: when you read a great book or watch a great talk, the value evaporates within weeks unless you capture it in a place AI can use later.

---

## Three Sub-Folders

```
wisdom/
├── index.md             # Register of every source you've processed
├── sources/             # One file per book / channel / podcast
├── voices/              # One file per person whose style/voice you want to clone
└── principles/          # Cross-source synthesis by domain
```

### `sources/`

One file per book, podcast, channel, course, etc. Each file extracts the principles, frameworks, and heuristics from that source — not summaries, not chapter notes. The actual *takeaways*.

Filename: `[source-slug].md` — e.g. `seeking-wisdom-bevelin.md`, `acquired-podcast-sk7.md`.

### `voices/`

One file per person whose copywriting, speaking style, framing, or voice you want to learn from or clone. Different from `sources/` — these are about *how someone communicates*, not what they teach.

Filename: `[person-slug].md` — e.g. `dan-koe.md`, `naval-ravikant.md`.

Use cases:
- Studying their writing style for inspiration.
- AI matching their tone when drafting in their style.
- Tracking what makes their voice distinctive.

### `principles/`

Cross-source synthesis. When you've read 5 books on negotiation, the *patterns across them* live here. One file per domain.

Filename: `[domain].md` — e.g. `negotiation.md`, `decision-making.md`, `email-copywriting.md`.

These are the highest-leverage files in the whole wisdom layer. They become the canonical reference AI uses when you ask questions in that domain.

---

## How to Use It

When you finish a book / podcast / course:

1. Add an entry to `index.md` (date, title, why you read it, rating).
2. Create the source file in `sources/` and extract the principles.
3. Cross-pollinate — if these principles apply to a domain you already have a `principles/` file for, update that file too.

When AI is helping you with something domain-specific:

- Tell it to read the relevant `principles/` file before answering.
- Or ask it directly: *"Using my wisdom layer principles for [domain], what would you do here?"*

---

## What NOT to Put Here

- Personal journal reflections (those go in `journal/`).
- Tactics specific to your business (those go in entity playbooks/frameworks).
- Quotes you liked but can't articulate why (force yourself — what's the principle?).

The wisdom layer is for **principles you can apply across contexts**. If a takeaway is too specific to apply elsewhere, it's not wisdom — it's a note.

---

## Worked Example

See `sources/example-book.md` for a worked example of how a single source file is structured.

See `voices/_template.md` for the template to use when capturing someone's voice.
