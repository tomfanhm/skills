# Toolbar Primitive

A container designed for organizing a collection of controls, such as buttons, toggle groups, or dropdown menus.

## Overview

Horizontal toolbar with ToggleGroup, ToggleItem, Button, Separator, and Link sub-components.

## Installation

```bash
npx expo install @rn-primitives/toolbar
```

**Shared primitive dependencies (manual install):** Slot, Types, Utils

## Usage

```tsx
import * as ToolbarPrimitive from "@rn-primitives/toolbar";

<ToolbarPrimitive.Root>
  <ToolbarPrimitive.ToggleGroup
    type="multiple"
    value={multipleValue}
    onValueChange={setMultipleValue}
  >
    <ToolbarPrimitive.ToggleItem value="bold">
      <Text>Bold</Text>
    </ToolbarPrimitive.ToggleItem>
    <ToolbarPrimitive.ToggleItem value="italic">
      <Text>Italic</Text>
    </ToolbarPrimitive.ToggleItem>
  </ToolbarPrimitive.ToggleGroup>
  <ToolbarPrimitive.Separator />
  <ToolbarPrimitive.Button>
    <Text>Button</Text>
  </ToolbarPrimitive.Button>
</ToolbarPrimitive.Root>;
```

## Props

### Root

Extends `View` props

| Prop        | Type                       | Note                      |
| ----------- | -------------------------- | ------------------------- |
| asChild     | boolean                    | _(optional)_              |
| orientation | 'horizontal' \| 'vertical' | **Web only** _(optional)_ |
| dir         | 'ltr' \| 'rtl'             | **Web only** _(optional)_ |
| loop        | boolean                    | **Web only** _(optional)_ |

### ToggleGroup

Extends `View` props

| Prop            | Type                                           | Note         |
| --------------- | ---------------------------------------------- | ------------ |
| type\*          | 'single' \| 'multiple'                         |              |
| value\*         | string \| undefined \| string[]                |              |
| onValueChange\* | (val: string \| undefined \| string[]) => void |              |
| asChild         | boolean                                        | _(optional)_ |
| disabled        | boolean                                        | _(optional)_ |

### ToggleItem

Extends `Pressable` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| value\* | string  |              |
| asChild | boolean | _(optional)_ |

### Separator

Extends `View` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Link

Extends `Pressable` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |
