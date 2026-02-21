# Navigation Menu Primitive

A collection of navigation links.

## Overview

Accessible navigation menu with expandable content panels and portal support.

## Installation

```bash
npx expo install @rn-primitives/navigation-menu
npx expo install @rn-primitives/portal
```

**Shared primitive dependencies (manual install):** Hooks, Portal, Slot, Types, Utils

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

> **⚠️ Note (Native):** You must handle closing menus when pressing/clicking outside the navigation menu, e.g., when navigating to another screen.

```tsx
import * as NavigationMenuPrimitive from "@rn-primitives/navigation-menu";

<NavigationMenuPrimitive.Root value={value} onValueChange={setValue}>
  <NavigationMenuPrimitive.List>
    <NavigationMenuPrimitive.Item value="getting-started">
      <NavigationMenuPrimitive.Trigger>
        <Text>Getting started</Text>
      </NavigationMenuPrimitive.Trigger>
      <NavigationMenuPrimitive.Portal>
        <NavigationMenuPrimitive.Content>
          <NavigationMenuPrimitive.Link>
            <Text>react-native-reusables</Text>
          </NavigationMenuPrimitive.Link>
        </NavigationMenuPrimitive.Content>
      </NavigationMenuPrimitive.Portal>
    </NavigationMenuPrimitive.Item>
  </NavigationMenuPrimitive.List>
</NavigationMenuPrimitive.Root>;
```

## Props

### Root

Extends `View` props

| Prop              | Type                                 | Note                      |
| ----------------- | ------------------------------------ | ------------------------- |
| value\*           | string \| undefined                  |                           |
| onValueChange\*   | (value: string \| undefined) => void |                           |
| asChild           | boolean                              | _(optional)_              |
| delayDuration     | number                               | **Web only** _(optional)_ |
| skipDelayDuration | number                               | **Web only** _(optional)_ |
| dir               | 'ltr' \| 'rtl'                       | **Web only** _(optional)_ |
| orientation       | 'horizontal' \| 'vertical'           | **Web only** _(optional)_ |

### List

Extends `View` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Item

Extends `Pressable` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| value\* | string  |              |
| asChild | boolean | _(optional)_ |

### Trigger

Extends `Pressable` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Portal

| Prop       | Type                             | Note                      |
| ---------- | -------------------------------- | ------------------------- |
| children\* | React.ReactNode                  |                           |
| forceMount | true \| undefined                | _(optional)_              |
| hostName   | string                           | **Web only** _(optional)_ |
| container  | HTMLElement \| null \| undefined | **Web only** _(optional)_ |

### Content

Extends `View` props

| Prop                    | Type                                         | Note                         |
| ----------------------- | -------------------------------------------- | ---------------------------- |
| asChild                 | boolean                                      | _(optional)_                 |
| forceMount              | true \| undefined                            | _(optional)_                 |
| alignOffset             | number                                       | **Native only** _(optional)_ |
| insets                  | Insets                                       | **Native only** _(optional)_ |
| avoidCollisions         | boolean                                      | **Native only** _(optional)_ |
| align                   | 'start' \| 'center' \| 'end'                 | **Native only** _(optional)_ |
| side                    | 'top' \| 'bottom'                            | **Native only** _(optional)_ |
| sideOffset              | number                                       | **Native only** _(optional)_ |
| disablePositioningStyle | boolean                                      | **Native only** _(optional)_ |
| loop                    | boolean                                      | **Web only** _(optional)_    |
| onEscapeKeyDown         | (event: KeyboardEvent) => void               | **Web only** _(optional)_    |
| onPointerDownOutside    | (event: PointerDownOutsideEvent) => void     | **Web only** _(optional)_    |
| onFocusOutside          | (event: FocusOutsideEvent) => void           | **Web only** _(optional)_    |
| onInteractOutside       | PointerDownOutsideEvent \| FocusOutsideEvent | **Web only** _(optional)_    |

### Link

Extends `Pressable` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| active  | boolean | _(optional)_ |
| asChild | boolean | _(optional)_ |

### Viewport

**Web only** — Extends `View` props (except `children`). Only renders on web.

### Indicator

Extends `View` props. No additional props.

## Context Hooks

### useRootContext

Must be used within a `Root` component. Provides: `value`, `onValueChange`.

### useItemContext

Must be used within an `Item` component. Provides: `value`.
