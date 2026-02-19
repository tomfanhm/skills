---
name: drizzle
description: Setup and configuration guide for Drizzle ORM. Use when setting up a new database, configuring schema, or running migrations.
---

# Drizzle ORM Skill

## Purpose
This skill guides you through the "Golden Path" setup for Drizzle ORM, covering installation, configuration, schema management, and migrations.

## When to Use
- Setting up a new database connection (Postgres, Neon, MySQL, SQLite).
- Configuring `drizzle.config.ts` for type-safe migrations.
- Defining schema using the modular `src/db/schema/*` pattern.
- Running migrations (`drizzle-kit generate` vs `push`).
- Seeding the database.

## Instructions

### 1. Installation

Install the core ORM and the Kit CLI:

```bash
npm install drizzle-orm
npm install -D drizzle-kit
```

Install the driver (Standard Postgres recommendation):
```bash
npm install postgres
```
*(For Neon, use `@neondatabase/serverless`)*

### 2. Configuration (`drizzle.config.ts`)

Use `defineConfig` for type safety. See `assets/drizzle.config.ts`.

Key settings:
- **schema**: Path to your schema file/folder (e.g., `./src/db/schema.ts` or `./src/db/schema/index.ts`).
- **out**: Directory for migration artifacts (default: `./drizzle`).
- **dialect**: Explicitly set to 'postgresql', 'mysql', or 'sqlite'.

### 3. Schema Management

**Golden Path**: Use a **Modular Schema** structure.
- Create `src/db/schema/` directory.
- Define tables in separate files (e.g., `users.ts`, `posts.ts`).
- Export everything in `src/db/schema/index.ts`.

```typescript
// src/db/schema/users.ts
import { pgTable, serial, text } from 'drizzle-orm/pg-core';
export const users = pgTable('users', {
  id: serial('id').primaryKey(),
  name: text('name'),
});
```

### 4. Database Connection (`db.ts`)

Instantiate the client and ORM instance. See `assets/db.ts`.

```typescript
import { drizzle } from 'drizzle-orm/postgres-js';
import postgres from 'postgres';
import * as schema from './schema';

const client = postgres(process.env.DATABASE_URL!);
export const db = drizzle(client, { schema });
```

### 5. Migration Workflow

**Development (Rapid Prototyping):**
Use `push` to sync schema directly to the DB without generating files.
```bash
npx drizzle-kit push
```

**Production (Version Control):**
Use `generate` to create SQL migration files, then apply them.
```bash
npx drizzle-kit generate
npx drizzle-kit migrate
```

### 6. Seeding

Use `drizzle-seed` or a custom script.
```bash
npx tsx src/db/seed.ts
```

## Examples

### Defining a Relation
```typescript
import { relations } from 'drizzle-orm';
import { users, posts } from './schema';

export const usersRelations = relations(users, ({ many }) => ({
  posts: many(posts),
}));
```
