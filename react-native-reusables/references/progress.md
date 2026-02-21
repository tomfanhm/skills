# Progress Primitive

Shows an indicator representing the advancement status of a task.

## Overview

Accessible progress bar with a root container and an indicator sub-component.

## Installation

```bash
npx expo install @rn-primitives/progress
```

**Shared primitive dependencies (manual install):** Types, Slot

## Usage

```tsx
import * as ProgressPrimitive from "@rn-primitives/progress";

<ProgressPrimitive.Root value={50} max={100}>
  <ProgressPrimitive.Indicator />
</ProgressPrimitive.Root>;
```

## Props

### Root

Extends `View` props

| Prop          | Type                                   | Note         |
| ------------- | -------------------------------------- | ------------ |
| value         | number \| null \| undefined            |              |
| asChild       | boolean                                | _(optional)_ |
| max           | number                                 | _(optional)_ |
| getValueLabel | (value: number, max: number) => string | _(optional)_ |

### Indicator

Extends `View` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |
