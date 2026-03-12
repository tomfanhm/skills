# Skills

A collection of reusable [Agent Skills](https://agentskills.io/specification) for development tooling and UI component libraries.

## Available Skills

| Skill | Description |
|-------|-------------|
| [drizzle](drizzle/SKILL.md) | Drizzle ORM setup, schema management, and migrations |
| [tailwind](tailwind/SKILL.md) | Tailwind CSS v3.4 setup, theming, and utilities |
| [turborepo](turborepo/SKILL.md) | Turborepo monorepo setup, pipelines, and caching |
| [react-native-reusables](react-native-reusables/SKILL.md) | Universal React Native UI components with shadcn/ui patterns |

## Structure

Each skill follows the [agentskills.io specification](https://agentskills.io/specification):

```
skill-name/
├── SKILL.md          # Main instructions (loaded on activation)
├── assets/           # Templates and config files
└── references/       # Detailed docs (loaded on demand)
```

## Usage

Install individual skills via [skills.sh](https://skills.sh) or copy the skill directory into your project.
