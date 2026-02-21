# Collapsible Primitive

A dynamic element that facilitates the expansion or collapse of a panel.

## Overview

Controlled collapsible panel with trigger and content sub-components.

## Installation

```bash
npx expo install @rn-primitives/collapsible
```

**Shared primitive dependencies (manual install):** Hooks, Slot, Types

## Usage

```tsx
import * as CollapsiblePrimitive from "@rn-primitives/collapsible";

<CollapsiblePrimitive.Root>
  <CollapsiblePrimitive.Trigger>
    <Text>Toggle</Text>
  </CollapsiblePrimitive.Trigger>
  <CollapsiblePrimitive.Content>
    <Text>Content</Text>
  </CollapsiblePrimitive.Content>
</CollapsiblePrimitive.Root>;
```

## Props

### Root

Extends `View` props

| Prop         | Type                     | Note         |
| ------------ | ------------------------ | ------------ |
| asChild      | boolean                  | _(optional)_ |
| open         | boolean                  | _(optional)_ |
| onOpenChange | (value: boolean) => void | _(optional)_ |
| defaultOpen  | boolean                  | _(optional)_ |
| disabled     | boolean                  | _(optional)_ |

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
