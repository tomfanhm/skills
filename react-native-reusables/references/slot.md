# Slot Primitive

Merges its props onto its immediate child.

## Overview

Can be used to support your own `asChild` prop. Available slot types: `View`, `Pressable`, `Text`, `Image`.

## Installation

```bash
npx expo install @rn-primitives/slot
```

## Usage

### View Slot

```tsx
import * as Slot from "@rn-primitives/slot";

function CustomView({ isChild = true }) {
  const Component = isChild ? Slot.View : View;
  return (
    <Component className="bg-red-500">
      {/* className is passed down to the child View when isChild is true */}
      <View key="x" />
    </Component>
  );
}
```

### Pressable Slot

```tsx
import * as Slot from "@rn-primitives/slot";

function CustomPressable() {
  return (
    <Slot.Pressable onPress={() => console.log("Pressed")}>
      {/* onPress is passed down to the child Pressable */}
      <Pressable />
    </Slot.Pressable>
  );
}
```

### Text Slot

```tsx
import * as Slot from "@rn-primitives/slot";

function CustomText() {
  return (
    <Slot.Text className="text-blue-500">
      <Text />
    </Slot.Text>
  );
}
```

### Image Slot

```tsx
import * as Slot from "@rn-primitives/slot";

function CustomImage() {
  return (
    <Slot.Image source={{ uri: "https://example.com/avatar.png" }}>
      <Image />
    </Slot.Image>
  );
}
```

## Props

Each slot variant inherits all props from its corresponding React Native component:

| Slot             | Inherits from     |
| ---------------- | ----------------- |
| `Slot.View`      | `View` props      |
| `Slot.Pressable` | `Pressable` props |
| `Slot.Text`      | `Text` props      |
| `Slot.Image`     | `Image` props     |
