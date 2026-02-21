# Utils Primitive

A collection of utilities for core primitives.

## Overview

Two utilities: `ToggleGroupUtils` for toggle group state management, and `EmptyGestureResponderEvent` for accessibility-safe event firing.

## Installation

```bash
npx expo install @rn-primitives/utils
```

## Usage

### ToggleGroupUtils

Helper functions for toggle group value state:

- `getIsSelected(value, itemValue)` — Returns `true` if the item is selected
- `getNewSingleValue(value, itemValue)` — Returns the new value for a single-select toggle group
- `getNewMultipleValue(value, itemValue)` — Returns the new value for a multi-select toggle group

```tsx
import { ToggleGroupUtils } from "@rn-primitives/utils";

function onPress(ev: GestureResponderEvent) {
  if (type === "single") {
    onValueChange(ToggleGroupUtils.getNewSingleValue(value, itemValue));
  }
  if (type === "multiple") {
    onValueChange(ToggleGroupUtils.getNewMultipleValue(value, itemValue));
  }
}

const isChecked =
  type === "single"
    ? ToggleGroupUtils.getIsSelected(value, itemValue)
    : undefined;
```

### EmptyGestureResponderEvent

Used for calling `onPress` and `onLongPress` without arguments, for accessibility purposes (e.g., keyboard Enter/Space key handling on web).

```tsx
import { EmptyGestureResponderEvent } from "@rn-primitives/utils";

function onKeyDown(ev: React.KeyboardEvent) {
  if (ev.key === "Enter" || ev.key === " ") {
    onPressProp?.(EmptyGestureResponderEvent);
  }
}
```
