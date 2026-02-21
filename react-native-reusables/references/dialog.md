# Dialog Primitive

A modal dialog that interrupts the user with important content and expects a response.

## Overview

Full-featured modal dialog with portal support, overlay, title, description, and close button.

## Installation

```bash
npx expo install @rn-primitives/dialog
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
import * as DialogPrimitive from "@rn-primitives/dialog";

<DialogPrimitive.Root>
  <DialogPrimitive.Trigger>
    <Text>Show Dialog</Text>
  </DialogPrimitive.Trigger>
  <DialogPrimitive.Portal>
    <DialogPrimitive.Overlay>
      <DialogPrimitive.Content>
        <DialogPrimitive.Title>Dialog Title</DialogPrimitive.Title>
        <DialogPrimitive.Description>
          Dialog description.
        </DialogPrimitive.Description>
        <DialogPrimitive.Close>
          <Text>Close</Text>
        </DialogPrimitive.Close>
      </DialogPrimitive.Content>
    </DialogPrimitive.Overlay>
  </DialogPrimitive.Portal>
</DialogPrimitive.Root>;
```

## Props

### Root

Extends `View` props

| Prop         | Type                     | Note         |
| ------------ | ------------------------ | ------------ |
| asChild      | boolean                  | _(optional)_ |
| open         | boolean                  | _(optional)_ |
| onOpenChange | (value: boolean) => void | _(optional)_ |
| defaultOpen  | boolean                  | _(optional)_ |

### Trigger

Extends `Pressable` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

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

### Title

Extends `Text` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Description

Extends `Text` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Close

Extends `Pressable` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

## Context Hooks

### useRootContext

Must be used within a `Root` component. Provides: `open`, `onOpenChange`.
