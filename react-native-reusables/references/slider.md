# Slider Primitive

An input allowing the user to choose a value from a specified range.

## Overview

Range slider with track, range, and thumb sub-components. On native, gesture handling must be implemented manually.

## Installation

```bash
npx expo install @rn-primitives/slider
```

**Shared primitive dependencies (manual install):** Types, Slot

## Usage

> **⚠️ Caution (Native):** You must implement gesture handling yourself on native platforms. The slider does not handle touch/drag gestures automatically.

```tsx
import * as Slider from "@rn-primitives/slider";

const [value, setValue] = React.useState(50);

<Slider.Root
  value={value}
  onValueChange={(vals) => {
    const nextValue = vals[0];
    if (typeof nextValue !== "number") return;
    setValue(nextValue);
  }}
>
  <Slider.Track>
    <Slider.Range style={{ width: `${value}%` }} />
    <Slider.Thumb style={{ left: `${value}%` }} />
  </Slider.Track>
</Slider.Root>;
```

## Props

### Root

Extends `View` props

| Prop          | Type                      | Note                      |
| ------------- | ------------------------- | ------------------------- |
| value         | number                    | _(optional)_              |
| disabled      | boolean                   | _(optional)_              |
| min           | number                    | _(optional)_              |
| max           | number                    | _(optional)_              |
| dir           | 'ltr' \| 'rtl'            | **Web only** _(optional)_ |
| inverted      | boolean                   | **Web only** _(optional)_ |
| step          | number                    | **Web only** _(optional)_ |
| onValueChange | (value: number[]) => void | **Web only** _(optional)_ |

### Track

Extends `View` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Range

Extends `View` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Thumb

Extends `View` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |
