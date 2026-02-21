# Radio Group Primitive

A group of selectable buttons (radio buttons) wherein only one button can be checked at a time.

## Overview

Accessible radio group with item and indicator sub-components. Uses `aria-labelledby` for accessibility.

## Installation

```bash
npx expo install @rn-primitives/radio-group
```

**Shared primitive dependencies (manual install):** Types, Slot

## Usage

```tsx
import * as RadioGroupPrimitive from "@rn-primitives/radio-group";

const [value, setValue] = React.useState("Comfortable");

<RadioGroupPrimitive.Root value={value} onValueChange={setValue}>
  <View>
    <RadioGroupPrimitive.Item value="Default" aria-labelledby="default-label">
      <RadioGroupPrimitive.Indicator />
    </RadioGroupPrimitive.Item>
    <Text nativeID="default-label" onPress={() => setValue("Default")}>
      Default
    </Text>
  </View>
</RadioGroupPrimitive.Root>;
```

## Props

### Root

Extends `View` props

| Prop          | Type                  | Note         |
| ------------- | --------------------- | ------------ |
| value         | string \| undefined   |              |
| onValueChange | (val: string) => void |              |
| asChild       | boolean               | _(optional)_ |
| disabled      | boolean               | _(optional)_ |

### Item

Extends `Pressable` props

| Prop              | Type    | Note                                          |
| ----------------- | ------- | --------------------------------------------- |
| value\*           | string  |                                               |
| aria-labelledby\* | string  | Must match the `nativeID` of the label `Text` |
| asChild           | boolean | _(optional)_                                  |

### Indicator

Extends `View` props

| Prop       | Type    | Note         |
| ---------- | ------- | ------------ |
| forceMount | boolean | _(optional)_ |
| asChild    | boolean | _(optional)_ |
