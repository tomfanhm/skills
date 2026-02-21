# Checkbox Primitive

A box that is a checked (ticked) indicator when activated.

## Overview

Controlled checkbox component with indicator support across all platforms.

## Installation

```bash
npx expo install @rn-primitives/checkbox
```

**Shared primitive dependencies (manual install):** Types, Hooks, Slot

## Usage

```tsx
import * as CheckboxPrimitive from "@rn-primitives/checkbox";

const [checked, setChecked] = React.useState(false);

<CheckboxPrimitive.Root checked={checked} onCheckedChange={setChecked}>
  <CheckboxPrimitive.Indicator>
    <View style={{ height: 12, width: 12, backgroundColor: "red" }} />
  </CheckboxPrimitive.Indicator>
</CheckboxPrimitive.Root>;
```

## Props

### Root

Extends `Pressable` props

| Prop              | Type                       | Note         |
| ----------------- | -------------------------- | ------------ |
| checked\*         | boolean                    |              |
| onCheckedChange\* | (checked: boolean) => void |              |
| disabled          | boolean                    | _(optional)_ |

### Indicator

Extends `View` props

| Prop       | Type              | Note         |
| ---------- | ----------------- | ------------ |
| forceMount | true \| undefined | _(optional)_ |
