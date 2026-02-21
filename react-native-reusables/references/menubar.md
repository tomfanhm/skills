# Menubar Primitive

A menu that stays visible on the screen, often seen in desktop apps, offering easy access to a standard set of commands.

## Overview

Persistent menubar with multiple menus, sub-menus, checkbox items, and radio groups.

## Installation

```bash
npx expo install @rn-primitives/menubar
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

> **⚠️ Note (Native):** You must handle closing menus when pressing/clicking outside the menubar component, e.g., when navigating to another screen.

```tsx
import * as MenubarPrimitive from "@rn-primitives/menubar";

<MenubarPrimitive.Root value={value} onValueChange={onValueChange}>
  <MenubarPrimitive.Menu value="file">
    <MenubarPrimitive.Trigger>
      <Text>File</Text>
    </MenubarPrimitive.Trigger>
    <MenubarPrimitive.Portal>
      <MenubarPrimitive.Content>
        <MenubarPrimitive.Item>
          <Text>New Tab</Text>
        </MenubarPrimitive.Item>
      </MenubarPrimitive.Content>
    </MenubarPrimitive.Portal>
  </MenubarPrimitive.Menu>
</MenubarPrimitive.Root>;
```

## Props

### Root

Extends `View` props

| Prop            | Type                                 | Note         |
| --------------- | ------------------------------------ | ------------ |
| value\*         | string \| undefined                  |              |
| onValueChange\* | (value: string \| undefined) => void |              |
| asChild         | boolean                              | _(optional)_ |

### Menu

Extends `View` props

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

Must be used within a `Root` component. Provides: `value`, `onValueChange`.

### useMenuContext

Must be used within a `Menu` component. Provides: `open`, `onOpenChange`.

### useSubContext

Must be used within a `Sub` component. Provides: `open`, `onOpenChange`.
