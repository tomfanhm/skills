# Toast Primitive

A concise message that appears briefly.

## Overview

Toast notification component. Requires manual timer management and uses the Portal primitive for positioning.

## Installation

```bash
npx expo install @rn-primitives/toast
npx expo install @rn-primitives/portal
```

**Shared primitive dependencies (manual install):** Slot, Types

## Usage

> **⚠️ Caution:** Requires a `<PortalHost />` as the last child of your `<Root/>` (`app/_layout.tsx`) component.
>
> ```tsx
> import { PortalHost } from "@rn-primitives/portal";
>
> function Root() {
>   return (
>     <>
>       <Stack />
>       <PortalHost />
>     </>
>   );
> }
> ```

> **⚠️ Note (Native):** There is no built-in auto-dismiss timer. You must implement your own countdown and call `setOpen(false)` when it expires.

```tsx
import { Portal } from "@rn-primitives/portal";
import * as ToastPrimitive from "@rn-primitives/toast";
import { useSafeAreaInsets } from "react-native-safe-area-context";

function Example() {
  const [open, setOpen] = React.useState(false);
  const insets = useSafeAreaInsets();

  return (
    <>
      {open && (
        <Portal name="toast-example">
          <View
            style={{ top: insets.top + 4, position: "absolute", width: "100%" }}
          >
            <ToastPrimitive.Root
              type="foreground"
              open={open}
              onOpenChange={setOpen}
            >
              <ToastPrimitive.Title>Here is a toast</ToastPrimitive.Title>
              <ToastPrimitive.Description>
                Toast message
              </ToastPrimitive.Description>
              <ToastPrimitive.Action>
                <Text>Action</Text>
              </ToastPrimitive.Action>
              <ToastPrimitive.Close>
                <Text>Close</Text>
              </ToastPrimitive.Close>
            </ToastPrimitive.Root>
          </View>
        </Portal>
      )}
    </>
  );
}
```

## Props

### Root

Extends `View` props

| Prop           | Type                         | Note                                  |
| -------------- | ---------------------------- | ------------------------------------- |
| open\*         | boolean                      |                                       |
| onOpenChange\* | (open: boolean) => void      |                                       |
| type           | 'foreground' \| 'background' | Defaults to `foreground` _(optional)_ |
| asChild        | boolean                      | _(optional)_                          |

### Action

Extends `Pressable` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Close

Extends `Pressable` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Title

Extends `Text` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Description

Extends `Text` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |
