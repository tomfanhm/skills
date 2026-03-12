---
name: tailwind
description: "Setup and configuration guide for Tailwind CSS v3.4 with theme, plugins, and utility setup. WHEN: \"set up Tailwind\", \"configure Tailwind theme\", \"add Tailwind CSS\", \"cn utility\", \"class merging\", \"Tailwind config\"."
---

# Tailwind CSS Skill

Golden-path setup for Tailwind CSS v3.4: installation, configuration, class sorting, and the `cn` utility.

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

See [the config template](assets/tailwind.config.js).

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

See [the cn implementation](assets/utils.ts).

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
