# Toggle Primitive

A button with a true or false state, which can be activated or deactivated by toggling.

## Overview

Single controlled toggle button with `pressed` / `onPressedChange` API.

## Installation

```bash
npx expo install @rn-primitives/toggle
```

**Shared primitive dependencies (manual install):** Slot, Types

## Usage

```tsx
import * as TogglePrimitive from "@rn-primitives/toggle";

const [isActive, setIsActive] = React.useState(false);

<TogglePrimitive.Root pressed={isActive} onPressedChange={setIsActive}>
  <Text>Bold</Text>
</TogglePrimitive.Root>;
```

## Props

### Root

Extends `Pressable` props

| Prop              | Type                   | Note         |
| ----------------- | ---------------------- | ------------ |
| pressed\*         | boolean                |              |
| onPressedChange\* | (val: boolean) => void |              |
| asChild           | boolean                | _(optional)_ |
| disabled          | boolean                | _(optional)_ |
