# Portal Primitive

Portals let you render children into a different part of your app.

## Overview

Native-only portal implementation (backed by zustand). Features: single default host, multiple hosts, multiple portals per host. On web, RN Primitives use `createPortal` from `react-dom` instead.

## Installation

```bash
npx expo install @rn-primitives/portal
```

**Manual install dependency:** `zustand`

```bash
npx expo install zustand
```

## Usage

### Default Portal

Add `<PortalHost />` as the last child of your root layout (`app/_layout.tsx`). Children of any `<Portal />` will render there.

```tsx
import { PortalHost } from "@rn-primitives/portal";

function Root() {
  return (
    <>
      <Stack />
      {/* Children of <Portal /> will render here */}
      <PortalHost />
    </>
  );
}
```

Then, from any component:

```tsx
import { Portal } from "@rn-primitives/portal";

function Card() {
  return (
    <Wrapper>
      <Content />
      <Portal name="card-portal">
        <View
          style={[
            StyleSheet.absoluteFill,
            { justifyContent: "center", alignItems: "center" },
          ]}
        >
          <Text>I am centered and overlay the entire screen</Text>
        </View>
      </Portal>
    </Wrapper>
  );
}
```

### Custom Portal Host

```tsx
import { Portal, PortalHost } from "@rn-primitives/portal";

function Example() {
  return (
    <Wrapper>
      <PortalHost name="example-host" />
      <Content />
      <Portal name="example-portal" hostName="example-host">
        <View>
          <Text>I will be rendered above the Content component</Text>
        </View>
      </Portal>
    </Wrapper>
  );
}
```

## Props

### PortalHost

| Prop | Type   | Note                                            |
| ---- | ------ | ----------------------------------------------- |
| name | string | Provide when used as a custom host _(optional)_ |

### Portal

| Prop     | Type   | Note                                                           |
| -------- | ------ | -------------------------------------------------------------- |
| name\*   | string | Must be unique — portals with the same name replace each other |
| hostName | string | Provide when rendering in a custom host _(optional)_           |
