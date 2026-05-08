---
title: "Entity Structure"
entity: shared
type: reference
tags: [entities, structure, register]
updated: 2026-Jan-15
status: draft
---

# Entity Structure

> Master register of every business, brand, trust, project, or initiative you run. The single source of truth for "what entities exist and how do they relate."
>
> AI uses this to know:
> - Which entity a given task or file belongs to
> - The entity code prefix to use on new files
> - The legal or organisational structure when relevant
> - The relationships between entities (e.g. holding company → subsidiary)

---

## Entity Codes

Every entity gets a two-letter code. The code prefixes every file in that entity's folder.

| Code | Entity name | Type | Status | My role |
|------|-------------|------|--------|---------|
| `[xx]` | [Entity name] | [Trading company / Trust / Brand / Project] | [Active / Pre-launch / Winding down / Dormant] | [Owner / Co-founder / Director / Advisor / Employee] |
| `[xx]` | [Entity name] | [Type] | [Status] | [Role] |

Reserved code:
- `shared` — for files that belong to no single entity (conventions, glossary, master context).

---

## Detail Per Entity

For each entity above, fill in a short profile here. Move to a dedicated `[entity]/[code]-entity.md` file when it grows beyond a paragraph.

### `[xx]` — [Entity name]

- **What it does:** [Plain-English description of what this entity actually delivers]
- **Who it serves:** [Customers, members, audience]
- **Status:** [Current operational state]
- **My role:** [Specific role and ownership %]
- **Other key people:** [Co-founders, directors, lead employees]
- **Year started:** [YYYY]
- **Public name vs legal name:** [If different]
- **ABN / company number / equivalent:** [If relevant — keep this in mind for invoicing/legal]
- **Bank account:** [Reference only — never store credentials here]
- **Website:** [URL]
- **Folder:** `[xx]/` in this HQ

---

## Relationships

If your entities are structured (holding company, subsidiaries, trusts), document the relationships here. A simple text tree works for most setups.

```
[Holding entity]
├── [Subsidiary 1]
├── [Subsidiary 2]
└── [Trust]
    └── [Asset / sub-entity]
```

Or describe in prose:
- *[Entity A] is a wholly-owned subsidiary of [Entity B].*
- *[Entity C] is a trading name of [Entity D]; not a separate legal entity.*
- *[Trust X] holds the assets of [Property Y].*

---

## Defunct / Former Names

If you've renamed entities or wound things down, record them here so the AI doesn't get confused by historical references in old documents.

| Former name | Current name (or status) | When changed |
|-------------|--------------------------|--------------|
| [Old name] | [New name / Wound up YYYY-Mon-DD] | [Date] |

---

## Decisions Worth Remembering

Major structural decisions about entity setup. Helps AI not re-litigate.

- **[YYYY-Mon-DD]** — [Decision and why]

---

## When to Update

- Whenever you start a new entity or wind one down.
- Whenever ownership %, role, or legal structure changes.
- Whenever you add a folder to HQ for a new entity.
