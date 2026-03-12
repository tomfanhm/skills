# Menubar Primitive

A menu that stays visible on the screen, often seen in desktop apps, offering easy access to a standard set of commands.

## Overview

Persistent menubar with multiple menus, sub-menus, checkbox items, and radio groups.

## Installation

```bash
npx expo install @rn-primitives/menubar
npx expo install @rn-primitives/portal
```

**Shared primitive dependencies (manual install):** Hooks, Portal, Slot, Types, Utils

## Usage

> **Caution:** Requires a `<PortalHost />` as the last child of your `<Root/>` (`app/_layout.tsx`) component.
>
> ```tsx
> import { PortalHost } from "@rn-primitives/portal";
>
> function Root() {
>   return (
>     <>
>       <Stack />
>       <PortalHost />
>     </>
>   );
> }
> ```

> **Note (Native):** You must handle closing menus when pressing/clicking outside the menubar component, e.g., when navigating to another screen.

```tsx
import * as MenubarPrimitive from "@rn-primitives/menubar";

<MenubarPrimitive.Root value={value} onValueChange={onValueChange}>
  <MenubarPrimitive.Menu value="file">
    <MenubarPrimitive.Trigger>
      <Text>File</Text>
    </MenubarPrimitive.Trigger>
    <MenubarPrimitive.Portal>
      <MenubarPrimitive.Content>
        <MenubarPrimitive.Item>
          <Text>New Tab</Text>
        </MenubarPrimitive.Item>
      </MenubarPrimitive.Content>
    </MenubarPrimitive.Portal>
  </MenubarPrimitive.Menu>
</MenubarPrimitive.Root>;
```

## Context Hooks

| Hook | Scope | Provides |
|------|-------|----------|
| `useRootContext` | `Root` | `value`, `onValueChange` |
| `useMenuContext` | `Menu` | `open`, `onOpenChange` |
| `useSubContext` | `Sub` | `open`, `onOpenChange` |

For full prop tables, see [Menubar Props](props.md).
