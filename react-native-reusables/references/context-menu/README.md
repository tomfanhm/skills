# Context Menu Primitive

Shows a menu activated by either a right-click or a long-press.

## Overview

Full-featured context menu with sub-menus, checkbox items, and radio groups. Activated on long-press (native) or right-click (web).

## Installation

```bash
npx expo install @rn-primitives/context-menu
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

```tsx
import * as ContextMenuPrimitive from "@rn-primitives/context-menu";

<ContextMenuPrimitive.Root>
  <ContextMenuPrimitive.Trigger>
    <Text>
      {Platform.OS === "web" ? "Right click here" : "Long press here"}
    </Text>
  </ContextMenuPrimitive.Trigger>
  <ContextMenuPrimitive.Portal>
    <ContextMenuPrimitive.Overlay>
      <ContextMenuPrimitive.Content>
        <ContextMenuPrimitive.Item>
          <Text>Back</Text>
        </ContextMenuPrimitive.Item>
        <ContextMenuPrimitive.Separator />
        <ContextMenuPrimitive.CheckboxItem
          checked={checkboxValue}
          onCheckedChange={setCheckboxValue}
          closeOnPress={false}
        >
          <Text>Show Bookmarks Bar</Text>
        </ContextMenuPrimitive.CheckboxItem>
      </ContextMenuPrimitive.Content>
    </ContextMenuPrimitive.Overlay>
  </ContextMenuPrimitive.Portal>
</ContextMenuPrimitive.Root>;
```

## Context Hooks

| Hook | Scope | Provides |
|------|-------|----------|
| `useRootContext` | `Root` | `open`, `onOpenChange` |
| `useSubContext` | `Sub` | `open`, `onOpenChange` |

For full prop tables, see [Context Menu Props](props.md).
