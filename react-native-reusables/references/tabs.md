# Tabs Primitive

A collection of layered content sections (tab panels) displayed individually.

## Overview

Controlled tabs component with List, Trigger, and Content sub-components.

## Installation

```bash
npx expo install @rn-primitives/tabs
```

**Shared primitive dependencies (manual install):** Types, Slot

## Usage

```tsx
import * as TabsPrimitive from "@rn-primitives/tabs";

const [value, setValue] = React.useState("account");

<TabsPrimitive.Root value={value} onValueChange={setValue}>
  <TabsPrimitive.List>
    <TabsPrimitive.Trigger value="account">
      <Text>Account</Text>
    </TabsPrimitive.Trigger>
    <TabsPrimitive.Trigger value="password">
      <Text>Password</Text>
    </TabsPrimitive.Trigger>
  </TabsPrimitive.List>
  <TabsPrimitive.Content value="account">
    <Text>Account content</Text>
  </TabsPrimitive.Content>
  <TabsPrimitive.Content value="password">
    <Text>Password content</Text>
  </TabsPrimitive.Content>
</TabsPrimitive.Root>;
```

## Props

### Root

Extends `View` props

| Prop            | Type                       | Note                      |
| --------------- | -------------------------- | ------------------------- |
| value\*         | string                     |                           |
| onValueChange\* | (value: string) => void    |                           |
| asChild         | boolean                    | _(optional)_              |
| disabled        | boolean                    | _(optional)_              |
| orientation     | 'horizontal' \| 'vertical' | **Web only** _(optional)_ |
| dir             | 'ltr' \| 'rtl'             | **Web only** _(optional)_ |
| activationMode  | 'automatic' \| 'manual'    | **Web only** _(optional)_ |

### List

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

| Prop       | Type    | Note         |
| ---------- | ------- | ------------ |
| value\*    | string  |              |
| forceMount | boolean | _(optional)_ |
| asChild    | boolean | _(optional)_ |

## Context Hooks

### useRootContext

Must be used within a `Root` component. Provides: `value`, `onValueChange`.

### useTriggerContext

Must be used within a `Trigger` component. Provides: `value`.
