# Hooks Primitive

A collection of hooks for core primitives.

## Overview

Three utility hooks used internally by rn-primitives: `useAugmentedRef`, `useControllableState`, and `useRelativePosition`.

## Installation

```bash
npx expo install @rn-primitives/hooks
```

## Usage

### useAugmentedRef

Allows using a forwarded ref as a value of `useRef` and adding properties to the ref.

```tsx
import { useAugmentedRef } from "@rn-primitives/hooks";

const augmentedRef = useAugmentedRef({ ref });
```

### useControllableState

Allows defaulting to an uncontrolled state and controlling the state from the parent.

```tsx
import { useControllableState } from "@rn-primitives/hooks";

const [open = false, onOpenChange] = useControllableState({
  prop: openProp,
  defaultProp: defaultOpen,
  onChange: onOpenChangeProp,
});
```

### useRelativePosition

Returns a style for an element relative to another element. **Used for native primitives only.**

```tsx
import { useRelativePosition } from "@rn-primitives/hooks";

const positionStyle = useRelativePosition({
  align,
  avoidCollisions,
  triggerPosition,
  contentLayout,
  alignOffset,
  insets,
  sideOffset,
  side,
  disablePositioningStyle,
});
```

## Props

### useAugmentedRef

| Prop    | Type                                     | Note                                      |
| ------- | ---------------------------------------- | ----------------------------------------- |
| ref\*   | React.Ref\<T>                            | Forwarded ref                             |
| methods | Record\<string, (...args: any[]) => any> | Methods added to the ref _(optional)_     |
| deps    | Array\<any>                              | Dependency array for methods _(optional)_ |

### useControllableState

| Prop        | Type                            | Note         |
| ----------- | ------------------------------- | ------------ |
| prop        | T \| undefined                  | _(optional)_ |
| defaultProp | T \| undefined                  | _(optional)_ |
| onChange    | (state: T \| undefined) => void | _(optional)_ |

### useRelativePosition

| Prop                      | Type                         | Note                                                                 |
| ------------------------- | ---------------------------- | -------------------------------------------------------------------- |
| align\*                   | 'start' \| 'center' \| 'end' | Horizontal alignment relative to trigger                             |
| avoidCollisions\*         | boolean                      | Prevent content from going offscreen                                 |
| triggerPosition\*         | LayoutPosition \| null       | Layout position of the trigger                                       |
| contentLayout\*           | LayoutRectangle \| null      | Layout size of the content                                           |
| alignOffset\*             | number                       | Horizontal offset                                                    |
| insets\*                  | LayoutRectangle              | Prevents content from going over insets when avoidCollisions is true |
| sideOffset\*              | number                       | Vertical offset                                                      |
| side\*                    | 'top' \| 'bottom'            | Side alignment relative to trigger                                   |
| disablePositioningStyle\* | boolean                      | Completely disables styling returned from hook                       |
