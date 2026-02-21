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

## Props

### Root

Extends `View` props

| Prop         | Type                    | Note         |
| ------------ | ----------------------- | ------------ |
| onOpenChange | (open: boolean) => void | _(optional)_ |
| asChild      | boolean                 | _(optional)_ |

### Trigger

Extends `Pressable` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

**Ref type `DropdownMenuTriggerRef`:**

| Method  | Note                     |
| ------- | ------------------------ |
| open()  | Opens the dropdown menu  |
| close() | Closes the dropdown menu |

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

| Prop                    | Type                                         | Note                         |
| ----------------------- | -------------------------------------------- | ---------------------------- |
| asChild                 | boolean                                      | _(optional)_                 |
| forceMount              | true \| undefined                            | _(optional)_                 |
| alignOffset             | number                                       | _(optional)_                 |
| insets                  | Insets                                       | _(optional)_                 |
| avoidCollisions         | boolean                                      | _(optional)_                 |
| align                   | 'start' \| 'center' \| 'end'                 | _(optional)_                 |
| side                    | 'top' \| 'bottom'                            | _(optional)_                 |
| sideOffset              | number                                       | _(optional)_                 |
| disablePositioningStyle | boolean                                      | **Native only** _(optional)_ |
| loop                    | boolean                                      | **Web only** _(optional)_    |
| onCloseAutoFocus        | (event: Event) => void                       | **Web only** _(optional)_    |
| onEscapeKeyDown         | (event: KeyboardEvent) => void               | **Web only** _(optional)_    |
| onPointerDownOutside    | (event: PointerDownOutsideEvent) => void     | **Web only** _(optional)_    |
| onFocusOutside          | (event: FocusOutsideEvent) => void           | **Web only** _(optional)_    |
| onInteractOutside       | PointerDownOutsideEvent \| FocusOutsideEvent | **Web only** _(optional)_    |
| collisionBoundary       | Element \| null \| Array\<Element \| null>   | **Web only** _(optional)_    |
| sticky                  | 'partial' \| 'always'                        | **Web only** _(optional)_    |
| hideWhenDetached        | boolean                                      | **Web only** _(optional)_    |

### Group

Extends `Text` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Label

Extends `Text` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Item

Extends `Pressable` props

| Prop         | Type    | Note         |
| ------------ | ------- | ------------ |
| asChild      | boolean | _(optional)_ |
| textValue    | string  | _(optional)_ |
| closeOnPress | boolean | _(optional)_ |

### CheckboxItem

Extends `Pressable` props

| Prop              | Type                     | Note                         |
| ----------------- | ------------------------ | ---------------------------- |
| checked\*         | boolean                  |                              |
| onCheckedChange\* | (value: boolean) => void |                              |
| textValue\*       | string                   |                              |
| asChild           | boolean                  | _(optional)_                 |
| closeOnPress      | boolean                  | **Native only** _(optional)_ |

### RadioGroup

Extends `View` props

| Prop            | Type                    | Note         |
| --------------- | ----------------------- | ------------ |
| value\*         | string                  |              |
| onValueChange\* | (value: string) => void |              |
| asChild         | boolean                 | _(optional)_ |

### RadioItem

Extends `Pressable` props

| Prop              | Type                     | Note                         |
| ----------------- | ------------------------ | ---------------------------- |
| value\*           | string                   |                              |
| onCheckedChange\* | (value: boolean) => void |                              |
| asChild           | boolean                  | _(optional)_                 |
| closeOnPress      | boolean                  | **Native only** _(optional)_ |

### ItemIndicator

Extends `View` props

| Prop       | Type              | Note         |
| ---------- | ----------------- | ------------ |
| asChild    | boolean           | _(optional)_ |
| forceMount | true \| undefined | _(optional)_ |

### Separator

Extends `View` props

| Prop       | Type    | Note         |
| ---------- | ------- | ------------ |
| asChild    | boolean | _(optional)_ |
| decorative | boolean | _(optional)_ |

### Sub

Extends `View` props

| Prop         | Type                     | Note         |
| ------------ | ------------------------ | ------------ |
| asChild      | boolean                  | _(optional)_ |
| defaultOpen  | boolean                  | _(optional)_ |
| open         | boolean                  | _(optional)_ |
| onOpenChange | (value: boolean) => void | _(optional)_ |

### SubTrigger

Extends `Pressable` props

| Prop      | Type    | Note         |
| --------- | ------- | ------------ |
| textValue | string  | _(optional)_ |
| asChild   | boolean | _(optional)_ |

### SubContent

Extends `Pressable` props

| Prop       | Type              | Note         |
| ---------- | ----------------- | ------------ |
| asChild    | boolean           | _(optional)_ |
| forceMount | true \| undefined | _(optional)_ |

## Context Hooks

### useRootContext

Must be used within a `Root` component. Provides: `open`, `onOpenChange`.

### useSubContext

Must be used within a `Sub` component. Provides: `open`, `onOpenChange`.
