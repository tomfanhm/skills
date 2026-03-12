# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

A multi-skill repository following the [agentskills.io specification](https://agentskills.io/specification). Each top-level directory is a standalone Agent Skill publishable to [skills.sh](https://skills.sh).

## Skill Authoring Rules

Every skill must comply with the agentskills.io spec:

- **SKILL.md** is the only required file. Frontmatter must have `name` (lowercase+hyphens, 1-64 chars, matches directory name) and `description` (≤60 words, uses `WHEN:` with quoted trigger phrases).
- **Token budgets**: SKILL.md < 5000 tokens (soft: 500). Reference files < 1000 tokens each — split oversized references into a folder with `README.md` + sub-files.
- **Reference loading is JIT**: Only files linked via proper markdown syntax `[text](references/file.md)` are loaded. Backtick paths and folder links do NOT trigger loading. Link to files, not directories.
- **Assets**: Link with `[description](assets/file.ext)`, not backtick paths.
- **No `DO NOT USE FOR:`** in descriptions (causes keyword contamination on Sonnet).
- **Self-contained references**: Each reference file must work standalone — no caching between requests.

## Structure Convention

```
skill-name/
├── SKILL.md              # Required: instructions with YAML frontmatter
├── assets/               # Optional: templates, config files
└── references/           # Optional: detailed docs (loaded on demand)
    ├── simple-topic.md   # Under 1000 tokens
    └── complex-topic/    # Split when over 1000 tokens
        ├── README.md     # Overview + links
        └── details.md    # Subtopic
```
