# Toggle Group Primitive

A collection of buttons with true or false states, which can be activated or deactivated by toggling.

## Overview

Toggle group supporting `single` and `multiple` selection modes.

## Installation

```bash
npx expo install @rn-primitives/toggle-group
```

**Shared primitive dependencies (manual install):** Slot, Types, Utils

## Usage

```tsx
import * as ToggleGroupPrimitive from "@rn-primitives/toggle-group";

const [multipleValue, setMultipleValue] = React.useState<string[]>([]);

<ToggleGroupPrimitive.Root
  type="multiple"
  value={multipleValue}
  onValueChange={setMultipleValue}
>
  <ToggleGroupPrimitive.Item value="bold">
    <Text>Bold</Text>
  </ToggleGroupPrimitive.Item>
  <ToggleGroupPrimitive.Item value="italic">
    <Text>Italic</Text>
  </ToggleGroupPrimitive.Item>
</ToggleGroupPrimitive.Root>;
```

## Props

### Root

Extends `View` props

| Prop            | Type                                           | Note                      |
| --------------- | ---------------------------------------------- | ------------------------- |
| type\*          | 'single' \| 'multiple'                         |                           |
| value\*         | string \| undefined \| string[]                |                           |
| onValueChange\* | (val: string \| undefined \| string[]) => void |                           |
| asChild         | boolean                                        | _(optional)_              |
| disabled        | boolean                                        | _(optional)_              |
| rovingFocus     | boolean                                        | **Web only** _(optional)_ |
| orientation     | 'horizontal' \| 'vertical'                     | **Web only** _(optional)_ |
| dir             | 'ltr' \| 'rtl'                                 | **Web only** _(optional)_ |
| ltr             | boolean                                        | **Web only** _(optional)_ |

### Item

Extends `Pressable` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| value\* | string  |              |
| asChild | boolean | _(optional)_ |

## Context Hooks

### useRootContext

Must be used within a `Root` component. Provides: `value`, `onValueChange`, `type`, `disabled`.

### useItemContext

Must be used within an `Item` component. Provides: `value`.
