# Select Primitive

Presents a selection of options for the user to choose from, activated by a button.

## Overview

Full-featured select with value object `{ value, label }`, portal support, and scroll buttons (web only).

## Installation

```bash
npx expo install @rn-primitives/select
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
import * as SelectPrimitive from "@rn-primitives/select";

<SelectPrimitive.Root defaultValue={{ value: "apple", label: "Apple" }}>
  <SelectPrimitive.Trigger>
    <SelectPrimitive.Value placeholder="Select a fruit" />
  </SelectPrimitive.Trigger>
  <SelectPrimitive.Portal>
    <SelectPrimitive.Overlay style={StyleSheet.absoluteFill}>
      <SelectPrimitive.Content>
        <SelectPrimitive.ScrollUpButton />
        <SelectPrimitive.Viewport>
          <SelectPrimitive.Group>
            <SelectPrimitive.Label>Fruits</SelectPrimitive.Label>
            <SelectPrimitive.Item label="Apple" value="apple">
              Apple
              <SelectPrimitive.ItemIndicator />
            </SelectPrimitive.Item>
          </SelectPrimitive.Group>
        </SelectPrimitive.Viewport>
        <SelectPrimitive.ScrollDownButton />
      </SelectPrimitive.Content>
    </SelectPrimitive.Overlay>
  </SelectPrimitive.Portal>
</SelectPrimitive.Root>;
```

## Props

### Root

Extends `View` props

| Prop          | Type                                                              | Note                      |
| ------------- | ----------------------------------------------------------------- | ------------------------- |
| defaultValue  | `{ value: string, label: string }` \| undefined                   | _(optional)_              |
| value         | `{ value: string, label: string }` \| undefined                   | _(optional)_              |
| onValueChange | (option: `{ value: string, label: string }` \| undefined) => void | _(optional)_              |
| onOpenChange  | (value: boolean) => void                                          | _(optional)_              |
| disabled      | boolean                                                           | _(optional)_              |
| asChild       | boolean                                                           | _(optional)_              |
| dir           | 'ltr' \| 'rtl'                                                    | **Web only** _(optional)_ |
| name          | string                                                            | **Web only** _(optional)_ |
| required      | boolean                                                           | **Web only** _(optional)_ |

### Trigger

Extends `Pressable` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

**Ref type `SelectTriggerRef`:**

| Method  | Note              |
| ------- | ----------------- |
| open()  | Opens the select  |
| close() | Closes the select |

### Value

Extends `Pressable` props

| Prop          | Type    | Note         |
| ------------- | ------- | ------------ |
| placeholder\* | string  |              |
| asChild       | boolean | _(optional)_ |

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

| Prop                    | Type                                    | Note                         |
| ----------------------- | --------------------------------------- | ---------------------------- |
| asChild                 | boolean                                 | _(optional)_                 |
| forceMount              | true \| undefined                       | _(optional)_                 |
| alignOffset             | number                                  | _(optional)_                 |
| insets                  | Insets                                  | _(optional)_                 |
| avoidCollisions         | boolean                                 | _(optional)_                 |
| align                   | 'start' \| 'center' \| 'end'            | _(optional)_                 |
| side                    | 'top' \| 'bottom'                       | _(optional)_                 |
| sideOffset              | number                                  | _(optional)_                 |
| disablePositioningStyle | boolean                                 | **Native only** _(optional)_ |
| position                | 'popper' \| 'item-aligned' \| undefined | **Web only** _(optional)_    |

### Item

Extends `Pressable` props

| Prop         | Type    | Note         |
| ------------ | ------- | ------------ |
| value\*      | string  |              |
| label\*      | string  |              |
| closeOnPress | boolean | _(optional)_ |
| asChild      | boolean | _(optional)_ |

### ItemText

Extends `Text` props (except `children`)

### ItemIndicator

Extends `View` props

| Prop       | Type    | Note         |
| ---------- | ------- | ------------ |
| forceMount | boolean | _(optional)_ |

### Group

Extends `View` props

### Label

Extends `Text` props

### Separator

Extends `View` props

### ScrollUpButton

**Web only** — Extends radix's select `ScrollUpButton` props. Only renders children on native.

### ScrollDownButton

**Web only** — Extends radix's select `ScrollDownButton` props. Only renders children on native.

### Viewport

**Web only** — Extends radix's select `Viewport` props. Only renders children on native.
