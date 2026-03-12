# Dropdown Menu Primitive

Shows a menu with options or actions when a user clicks the trigger button.

## Overview

Full-featured dropdown menu with sub-menus, checkbox items, radio groups, and portal support.

## Installation

```bash
npx expo install @rn-primitives/dropdown-menu
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
import * as DropdownMenuPrimitive from "@rn-primitives/dropdown-menu";

<DropdownMenuPrimitive.Root>
  <DropdownMenuPrimitive.Trigger>
    <Text>Open Dropdown Menu</Text>
  </DropdownMenuPrimitive.Trigger>
  <DropdownMenuPrimitive.Portal>
    <DropdownMenuPrimitive.Overlay style={StyleSheet.absoluteFill}>
      <DropdownMenuPrimitive.Content>
        <DropdownMenuPrimitive.Item>
          <Text>Back</Text>
        </DropdownMenuPrimitive.Item>
        <DropdownMenuPrimitive.Separator />
        <DropdownMenuPrimitive.CheckboxItem
          checked={checkboxValue}
          onCheckedChange={setCheckboxValue}
          closeOnPress={false}
        >
          <Text>Show Bookmarks Bar</Text>
          <DropdownMenuPrimitive.ItemIndicator />
        </DropdownMenuPrimitive.CheckboxItem>
      </DropdownMenuPrimitive.Content>
    </DropdownMenuPrimitive.Overlay>
  </DropdownMenuPrimitive.Portal>
</DropdownMenuPrimitive.Root>;
```

## Context Hooks

| Hook | Scope | Provides |
|------|-------|----------|
| `useRootContext` | `Root` | `open`, `onOpenChange` |
| `useSubContext` | `Sub` | `open`, `onOpenChange` |

For full prop tables, see [Dropdown Menu Props](props.md).
