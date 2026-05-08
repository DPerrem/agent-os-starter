# Skills

Skills are reusable capabilities that AI agents can invoke. Think of them as functions: each one teaches the AI how to do a specific thing well.

## What's Included

- **digital-filing** — the PATH methodology for file/folder organisation. Applies to your computer, cloud drives, and HQ itself.

## How Skills Work in Claude Code

Claude Code auto-discovers skills in a few places:

1. `~/.claude/skills/` — global skills (available in every project).
2. `./skills/` (relative to your working directory) — project skills.
3. Skills bundled inside a Claude Code plugin pack.

Each skill is a folder with a `SKILL.md` file at its root. The `SKILL.md` contains:
- Frontmatter declaring the skill's name, description, and trigger conditions.
- The actual content the AI loads when the skill is invoked.

When you (or the AI) invoke a skill, Claude Code reads `SKILL.md` and follows its instructions.

## Adding More Skills

Three options as you grow:

### 1. Use the public Claude Code skill marketplace

Browse community-built skills (via `/plugin` or by adding plugins to `~/.claude/plugins/`). Many high-quality skills exist for common tasks (web research, file processing, code review).

### 2. Build your own private skills repo

When you've collected several skills you want versioned and reusable across projects:

1. Create a private GitHub repo (e.g. `your-username/skills-private`).
2. Add a `skills/` folder inside it, with one folder per skill.
3. Clone it into your HQ at `./skills/` and gitignore that path.

### 3. Build skills inline

Drop a new folder into `./skills/[skill-name]/` with a `SKILL.md`. Claude Code picks it up immediately. Good for one-offs and experiments.

## Skill Anatomy

Minimum viable skill:

```
my-skill/
└── SKILL.md
```

`SKILL.md` frontmatter:

```yaml
---
name: my-skill
description: When to use this skill. Be specific — Claude reads this to decide whether to invoke it.
---
```

After the frontmatter, write the body — the instructions Claude follows when this skill is invoked.

Optional additions:
- `scripts/` — executable scripts the skill can run.
- `reference/` — reference material the skill links to but doesn't load by default.
- `walkthrough.md` — a step-by-step example.

## When to Build a Skill (vs Just Asking)

Build a skill when:
- You catch yourself giving the same set of instructions 3+ times.
- The instructions are long enough that copy-pasting is annoying.
- The pattern is reusable across multiple contexts (not specific to one entity).

Skip the skill and just ask when:
- It's a one-off task.
- The instructions are short (under 10 lines).
- You're still figuring out the pattern.

## Further Reading

- Anthropic's Claude Code documentation on skills.
- The included `digital-filing` skill — read it as a worked example of skill structure.
