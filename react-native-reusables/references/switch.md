# Switch Primitive

A control enabling the user to switch between a checked and unchecked state.

## Overview

Toggle switch with controlled state and thumb sub-component.

## Installation

```bash
npx expo install @rn-primitives/switch
```

**Shared primitive dependencies (manual install):** Types, Slot

## Usage

```tsx
import * as SwitchPrimitive from "@rn-primitives/switch";

const [checked, setChecked] = React.useState(false);

<SwitchPrimitive.Root checked={checked} onCheckedChange={setChecked}>
  <SwitchPrimitive.Thumb />
</SwitchPrimitive.Root>;
```

## Props

### Root

Extends `Pressable` props

| Prop              | Type                              | Note                      |
| ----------------- | --------------------------------- | ------------------------- |
| checked\*         | boolean                           |                           |
| onCheckedChange\* | (checked: boolean) => void        |                           |
| disabled          | boolean                           | _(optional)_              |
| asChild           | boolean                           | _(optional)_              |
| onKeyDown         | (ev: React.KeyboardEvent) => void | **Web only** _(optional)_ |

### Thumb

Extends `View` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |
