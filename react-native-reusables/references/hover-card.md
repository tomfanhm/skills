# Hover Card Primitive

Allows users to preview content hidden behind an element before hovering or pressing.

## Overview

A card that appears on hover (web) or press (native) with portal support.

## Installation

```bash
npx expo install @rn-primitives/hover-card
npx expo install @rn-primitives/portal
```

**Shared primitive dependencies (manual install):** Hooks, Portal, Slot, Types

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
import * as HoverCardPrimitive from "@rn-primitives/hover-card";

<HoverCardPrimitive.Root>
  <HoverCardPrimitive.Trigger>
    <Text>@nextjs</Text>
  </HoverCardPrimitive.Trigger>
  <HoverCardPrimitive.Content>
    <Text>The React Framework – created and maintained by @vercel.</Text>
  </HoverCardPrimitive.Content>
</HoverCardPrimitive.Root>;
```

## Props

### Root

Extends `View` props

| Prop         | Type                     | Note                         |
| ------------ | ------------------------ | ---------------------------- |
| onOpenChange | (value: boolean) => void | _(optional)_                 |
| asChild      | boolean                  | _(optional)_                 |
| relativeTo   | 'longPress' \| 'trigger' | **Native only** _(optional)_ |

### Trigger

Extends `Pressable` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

**Ref type `HoverCardTriggerRef`:**

| Method  | Note                  |
| ------- | --------------------- |
| open()  | Opens the hover card  |
| close() | Closes the hover card |

### Portal

| Prop       | Type                             | Note                      |
| ---------- | -------------------------------- | ------------------------- |
| children\* | React.ReactNode                  |                           |
| forceMount | true \| undefined                | _(optional)_              |
| hostName   | string                           | **Web only** _(optional)_ |
| container  | HTMLElement \| null \| undefined | **Web only** _(optional)_ |

### Overlay

Extends `Pressable` props

| Prop       | Type              | Note         |
| ---------- | ----------------- | ------------ |
| asChild    | boolean           | _(optional)_ |
| forceMount | true \| undefined | _(optional)_ |

### Content

Extends `View` props

| Prop                    | Type                                       | Note                         |
| ----------------------- | ------------------------------------------ | ---------------------------- |
| asChild                 | boolean                                    | _(optional)_                 |
| forceMount              | true \| undefined                          | _(optional)_                 |
| alignOffset             | number                                     | _(optional)_                 |
| insets                  | Insets                                     | _(optional)_                 |
| avoidCollisions         | boolean                                    | _(optional)_                 |
| align                   | 'start' \| 'center' \| 'end'               | _(optional)_                 |
| side                    | 'top' \| 'bottom'                          | _(optional)_                 |
| sideOffset              | number                                     | _(optional)_                 |
| disablePositioningStyle | boolean                                    | **Native only** _(optional)_ |
| collisionBoundary       | Element \| null \| Array\<Element \| null> | **Web only** _(optional)_    |
| sticky                  | 'partial' \| 'always'                      | **Web only** _(optional)_    |
| hideWhenDetached        | boolean                                    | **Web only** _(optional)_    |

## Context Hooks

### useRootContext

Must be used within a `Root` component. Provides: `open`, `onOpenChange`.
