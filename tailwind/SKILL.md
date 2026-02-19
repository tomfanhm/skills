---
name: tailwind
description: Setup and configuration guide for Tailwind CSS. Use when adding styling to a project, configuring themes, or setting up utility classes.
---

# Tailwind CSS Skill

## Purpose
This skill guides you through the "Golden Path" setup for Tailwind CSS v3.4, ensuring a production-ready configuration with optimal tooling.

## When to Use
- Starting a new web project (Next.js, Vite, etc.).
- configuring `tailwind.config.js` theme and plugins.
- Setting up class sorting and merging utilities (`cn`).
- Debugging styling conflicts.

## Instructions

### 1. Installation (v3.4)

**Standard Install:**
```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

**Next.js (App Router):**
Ensure `postcss.config.js` exists. Tailwind is often pre-installed, but verify plugins.

### 2. Configuration (`tailwind.config.js`)

**Golden Path Defaults:**
- **Content**: Explicit paths to avoid scanning `node_modules`.
- **Theme**: Use `extend` to preserve defaults.
- **Plugins**: Add `typography` and `forms` for robust baselines.

See `assets/tailwind.config.js` for the template.

### 3. Essential Tools

**Prettier Sorting:**
Install `prettier-plugin-tailwindcss` to enforce class order automatically. This prevents merge conflicts and maintains consistency.

```bash
npm install -D prettier prettier-plugin-tailwindcss
```

**Class Merging (`cn` utility):**
Use `clsx` + `tailwind-merge` to handle dynamic classes safely (especially for reusable components).

```bash
npm install clsx tailwind-merge
```

See `assets/utils.ts` for the implementation.

### 4. Global Styles (`globals.css`)

Use `@layer` directives to manage specificity.

```css
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer base {
  /* Define CSS variables for theming here */
  :root {
    --background: 0 0% 100%;
    --foreground: 222.2 84% 4.9%;
  }
}
```

## Examples

### Dynamic Component Styling
```tsx
import { cn } from "@/lib/utils"

export function Button({ className, ...props }) {
  return (
    <button 
      className={cn("bg-blue-500 hover:bg-blue-600", className)} 
      {...props} 
    />
  )
}
```
