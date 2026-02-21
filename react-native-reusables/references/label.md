# Label Primitive

A user-friendly label linked to controls for improved accessibility.

## Overview

Accessible label component that links to form controls via `nativeID` / `aria-labelledby`.

## Installation

```bash
npx expo install @rn-primitives/label
```

**Shared primitive dependencies (manual install):** Types, Slot

## Usage

```tsx
import * as LabelPrimitive from "@rn-primitives/label";

<LabelPrimitive.Root>
  <LabelPrimitive.Text nativeID="to-be-used-by-aria-labelledby-from-form-field">
    Label
  </LabelPrimitive.Text>
</LabelPrimitive.Root>;
```

## Props

### Root

Extends `Pressable` props (except `children` | `hitSlop` | `style`)

| Prop       | Type            | Note         |
| ---------- | --------------- | ------------ |
| children\* | React.ReactNode |              |
| style      | ViewStyle       | _(optional)_ |

### Text

Extends `Text` props

| Prop       | Type   | Note                                                                |
| ---------- | ------ | ------------------------------------------------------------------- |
| nativeID\* | string | Must match the `aria-labelledby` value of the associated form field |
| htmlFor    | string | **Web only**                                                        |
