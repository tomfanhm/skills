# Popover Primitive

Dynamic content within a portal, activated by a button press.

## Overview

Popover with portal support for rendering floating content above all other UI.

## Installation

```bash
npx expo install @rn-primitives/popover
npx expo install @rn-primitives/portal
```

**Shared primitive dependencies (manual install):** Types, Hooks, Slot, Portal

## Usage

> **⚠️ Caution:** Requires a `<PortalHost />` as the last child of your `<Root/>` (`app/_layout.tsx`) component.
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
import * as PopoverPrimitive from "@rn-primitives/popover";

<PopoverPrimitive.Root>
  <PopoverPrimitive.Trigger>
    <Text>Open Popover</Text>
  </PopoverPrimitive.Trigger>
  <PopoverPrimitive.Portal>
    <PopoverPrimitive.Content>
      <Text>Popover Content</Text>
    </PopoverPrimitive.Content>
  </PopoverPrimitive.Portal>
</PopoverPrimitive.Root>;
```

## Props

### Root

Extends `View` props

| Prop         | Type                     | Note         |
| ------------ | ------------------------ | ------------ |
| asChild      | boolean                  | _(optional)_ |
| onOpenChange | (value: boolean) => void | _(optional)_ |

### Trigger

Extends `Pressable` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

**Ref type `TriggerRef`:**

| Method  | Note               |
| ------- | ------------------ |
| open()  | Opens the popover  |
| close() | Closes the popover |

### Overlay

Extends `Pressable` props

| Prop         | Type              | Note         |
| ------------ | ----------------- | ------------ |
| asChild      | boolean           | _(optional)_ |
| forceMount   | true \| undefined | _(optional)_ |
| closeOnPress | boolean           | _(optional)_ |

### Portal

| Prop       | Type                             | Note                      |
| ---------- | -------------------------------- | ------------------------- |
| children\* | React.ReactNode                  |                           |
| forceMount | true \| undefined                | _(optional)_              |
| hostName   | string                           | **Web only** _(optional)_ |
| container  | HTMLElement \| null \| undefined | **Web only** _(optional)_ |

### Content

Extends `View` props

| Prop                    | Type                         | Note                         |
| ----------------------- | ---------------------------- | ---------------------------- |
| asChild                 | boolean                      | _(optional)_                 |
| forceMount              | true \| undefined            | _(optional)_                 |
| alignOffset             | number                       | **Native only** _(optional)_ |
| insets                  | Insets                       | **Native only** _(optional)_ |
| avoidCollisions         | boolean                      | **Native only** _(optional)_ |
| align                   | 'start' \| 'center' \| 'end' | **Native only** _(optional)_ |
| side                    | 'top' \| 'bottom'            | **Native only** _(optional)_ |
| sideOffset              | number                       | **Native only** _(optional)_ |
| disablePositioningStyle | boolean                      | **Native only** _(optional)_ |
| onOpenAutoFocus         | (ev: Event) => void          | **Web only** _(optional)_    |
| onCloseAutoFocus        | (ev: Event) => void          | **Web only** _(optional)_    |
| onEscapeKeyDown         | (ev: Event) => void          | **Web only** _(optional)_    |
| onInteractOutside       | (ev: Event) => void          | **Web only** _(optional)_    |
| onPointerDownOutside    | (ev: Event) => void          | **Web only** _(optional)_    |

### Close

Extends `Pressable` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

## Context Hooks

### useRootContext

Must be used within a `Root` component. Provides: `open`, `onOpenChange`.
