# Alert Dialog Primitive

A modal dialog that interrupts the user with important content and expects a response.

## Overview

Unstyled, accessible alert dialog with portal support for rendering above all other content.

## Installation

```bash
npx expo install @rn-primitives/alert-dialog
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
import * as AlertDialogPrimitive from "@rn-primitives/alert-dialog";

<AlertDialogPrimitive.Root>
  <AlertDialogPrimitive.Trigger>
    <Text>Show Alert Dialog</Text>
  </AlertDialogPrimitive.Trigger>
  <AlertDialogPrimitive.Portal>
    <AlertDialogPrimitive.Overlay>
      <AlertDialogPrimitive.Content>
        <AlertDialogPrimitive.Title>
          Are you absolutely sure?
        </AlertDialogPrimitive.Title>
        <AlertDialogPrimitive.Description>
          This action cannot be undone.
        </AlertDialogPrimitive.Description>
        <AlertDialogPrimitive.Cancel>
          <Text>Cancel</Text>
        </AlertDialogPrimitive.Cancel>
        <AlertDialogPrimitive.Action>
          <Text>Continue</Text>
        </AlertDialogPrimitive.Action>
      </AlertDialogPrimitive.Content>
    </AlertDialogPrimitive.Overlay>
  </AlertDialogPrimitive.Portal>
</AlertDialogPrimitive.Root>;
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

Extends `View` props

| Prop       | Type              | Note         |
| ---------- | ----------------- | ------------ |
| asChild    | boolean           | _(optional)_ |
| forceMount | true \| undefined | _(optional)_ |

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

### Cancel

Extends `Pressable` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Action

Extends `Pressable` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

## Context Hooks

### useRootContext

Must be used within a `Root` component. Provides: `open`, `onOpenChange`.
