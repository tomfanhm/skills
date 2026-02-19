---
name: turborepo
description: Setup and configuration guide for Turborepo monorepos. Use when starting a new monorepo, configuring pipelines, managing workspaces, or setting up remote caching.
---

# Turborepo Skill

## Purpose
This skill guides you through the setup, configuration, and management of a Turborepo monorepo, following the "Golden Path" for performance and scalability.

## When to Use
- Starting a new project with multiple packages/apps.
- Migrating an existing monorepo to Turborepo.
- Configuring `turbo.json` pipelines and caching strategy.
- Setting up remote caching (Vercel or self-hosted).
- optimizing CI/CD workflows with `turbo prune`.

## Instructions

### 1. Initialization

**Preferred Method (Golden Path):**
Use `create-turbo` to scaffold a production-ready monorepo with recommended structure (`apps/`, `packages/`).

```bash
npx create-turbo@latest
```

**Manual Setup (Migration):**
If migrating an existing repo:
1. Install turbo: `pnpm add turbo -D -w`
2. Create `turbo.json` at root (see Configuration).
3. Ensure workspace definition in `pnpm-workspace.yaml`.

### 2. Configuration (turbo.json)

The `turbo.json` file controls the task pipeline and caching behavior.

**Key Best Practices:**
- **dependsOn**: Use `^build` (upstream dependencies) to ensure topological build order.
- **outputs**: Explicitly define artifacts (`dist/**`, `.next/**`) to enable caching.
- **inputs**: Limit cache invalidation scope (e.g., `["src/**", "package.json"]`).
- **globalDependencies**: Track config files (`tsconfig.json`, `.env`) that affect all tasks.

**Example Pipeline:**
See `assets/turbo.json` for a starter template.

### 3. Workspace Management

**Package Manager:**
Use **pnpm** for best performance and strict dependency management.

**Structure:**
- `apps/*`: Application entry points (Next.js, Vite, etc.).
- `packages/*`: Shared internal libraries (UI kit, tsconfig, eslint-config).

**Workspace Config (`pnpm-workspace.yaml`):**
```yaml
packages:
  - "apps/*"
  - "packages/*"
```

**Internal Dependencies:**
Reference internal packages using `workspace:*` to ensure they link locally without publishing.
```json
"dependencies": {
  "@repo/ui": "workspace:*"
}
```

### 4. Remote Caching

Enable remote caching to share build artifacts across your team and CI.

**Vercel Managed:**
1. Authenticate: `npx turbo login`
2. Link project: `npx turbo link`

**Self-Hosted/Custom:**
Use environment variables or flags:
```bash
turbo build --api="https://my-cache.com" --token="xxxx"
```

### 5. CI/CD Optimization

**Pruning:**
Use `turbo prune` to generate a lightweight docker build context for a specific app.
```bash
# Generates a pruned /out directory with only necessary files
npx turbo prune --scope=web-app --docker
```

**CI Execution:**
Run tasks from the root. Let Turbo handle parallelization.
```bash
npx turbo build test lint
```

## Examples

### Adding a new shared package
1. Create folder `packages/utils`
2. Initialize `package.json` with name `@repo/utils`
3. Add export map (e.g., `"main": "./src/index.ts"`)
4. In consuming app: `pnpm add @repo/utils --filter web-app`

### Debugging Cache Misses
Run with `--dry=json` to see why a task is executing.
```bash
npx turbo build --dry=json
```
