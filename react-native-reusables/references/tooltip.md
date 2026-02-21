# Tooltip Primitive

A pop-up presenting relevant information when an element gains keyboard focus or the mouse hovers over it.

## Overview

Tooltip with portal support. On native it is triggered by press; on web by hover.

## Installation

```bash
npx expo install @rn-primitives/tooltip
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
import * as TooltipPrimitive from "@rn-primitives/tooltip";

<TooltipPrimitive.Root>
  <TooltipPrimitive.Trigger>
    <Text>{Platform.OS === "web" ? "Hover me" : "Press me"}</Text>
  </TooltipPrimitive.Trigger>
  <TooltipPrimitive.Portal>
    <TooltipPrimitive.Content>
      <Text>Tooltip Content</Text>
    </TooltipPrimitive.Content>
  </TooltipPrimitive.Portal>
</TooltipPrimitive.Root>;
```

## Props

### Root

Extends `View` props

| Prop                    | Type                     | Note                                        |
| ----------------------- | ------------------------ | ------------------------------------------- |
| asChild                 | boolean                  | _(optional)_                                |
| onOpenChange            | (value: boolean) => void | _(optional)_                                |
| delayDuration           | number                   | **Web only** — defaults to 700 _(optional)_ |
| skipDelayDuration       | number                   | **Web only** — defaults to 300 _(optional)_ |
| disableHoverableContent | boolean                  | _(optional)_                                |

### Trigger

Extends `Pressable` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

**Ref type `TooltipTriggerRef`:**

| Method  | Note               |
| ------- | ------------------ |
| open()  | Opens the tooltip  |
| close() | Closes the tooltip |

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

| Prop                    | Type                                       | Note                                             |
| ----------------------- | ------------------------------------------ | ------------------------------------------------ |
| asChild                 | boolean                                    | _(optional)_                                     |
| forceMount              | true \| undefined                          | _(optional)_                                     |
| alignOffset             | number                                     | _(optional)_                                     |
| insets                  | Insets                                     | _(optional)_                                     |
| avoidCollisions         | boolean                                    | _(optional)_                                     |
| align                   | 'start' \| 'center' \| 'end'               | _(optional)_                                     |
| side                    | 'top' \| 'bottom' \| 'left' \| 'right'     | `left` and `right` are **Web only** _(optional)_ |
| sideOffset              | number                                     | _(optional)_                                     |
| disablePositioningStyle | boolean                                    | **Native only** _(optional)_                     |
| collisionBoundary       | Element \| null \| Array\<Element \| null> | **Web only** _(optional)_                        |
| sticky                  | 'partial' \| 'always'                      | **Web only** _(optional)_                        |
| hideWhenDetached        | boolean                                    | **Web only** _(optional)_                        |
| onEscapeKeyDown         | (ev: Event) => void                        | **Web only** _(optional)_                        |
| onPointerDownOutside    | (ev: Event) => void                        | **Web only** _(optional)_                        |
