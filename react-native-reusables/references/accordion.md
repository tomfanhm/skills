# Accordion Primitive

A vertically stacked set of interactive headings that each reveal a section of content.

## Overview

Unstyled, accessible accordion component with a unified API across iOS, Android, and web.

## Installation

```bash
npx expo install @rn-primitives/accordion
```

**Shared primitive dependencies (manual install):** Types, Hooks, Slot

## Usage

```tsx
import * as AccordionPrimitive from "@rn-primitives/accordion";

<AccordionPrimitive.Root type="multiple" collapsible defaultValue={["item-1"]}>
  <AccordionPrimitive.Item value="item-1">
    <AccordionPrimitive.Trigger>
      <Text>Is it accessible?</Text>
    </AccordionPrimitive.Trigger>
    <AccordionPrimitive.Content>
      <Text>Yes. It adheres to the WAI-ARIA design pattern.</Text>
    </AccordionPrimitive.Content>
  </AccordionPrimitive.Item>
</AccordionPrimitive.Root>;
```

## Props

### Root

Extends `View` props

| Prop          | Type                                                    | Note                      |
| ------------- | ------------------------------------------------------- | ------------------------- |
| type\*        | 'single' \| 'multiple'                                  |                           |
| asChild       | boolean                                                 | _(optional)_              |
| defaultValue  | (string \| undefined) \| string[]                       | _(optional)_              |
| value         | (string \| undefined) \| string[]                       | _(optional)_              |
| onValueChange | ((string \| undefined) => void) \| ((string[]) => void) | _(optional)_              |
| dir           | 'ltr' \| 'rtl'                                          | **Web only** _(optional)_ |
| orientation   | 'vertical' \| 'horizontal'                              | **Web only** _(optional)_ |

### Item

Extends `View` props

| Prop     | Type    | Note         |
| -------- | ------- | ------------ |
| asChild  | boolean | _(optional)_ |
| value    | string  | _(optional)_ |
| disabled | boolean | _(optional)_ |

### Header

Extends `View` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Trigger

Extends `Pressable` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Content

Extends `View` props

| Prop       | Type              | Note         |
| ---------- | ----------------- | ------------ |
| asChild    | boolean           | _(optional)_ |
| forceMount | true \| undefined | _(optional)_ |

## Context Hooks

### useRootContext

Must be used within a `Root` component. Provides: `type`, `disabled`, `collapsible`, `value`, `onValueChange`.

### useItemContext

Must be used within an `Item` component. Provides: `value`, `disabled`, `isExpanded`.
