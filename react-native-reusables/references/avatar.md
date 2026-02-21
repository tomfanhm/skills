# Avatar Primitive

An image component featuring an alternative representation for depicting the user.

## Overview

Displays a user avatar with image fallback support across all platforms.

## Installation

```bash
npx expo install @rn-primitives/avatar
```

**Shared primitive dependencies (manual install):** Types, Slot

## Usage

```tsx
import * as AvatarPrimitive from "@rn-primitives/avatar";

const GITHUB_AVATAR_URI = "https://github.com/mrzachnugent.png";

<AvatarPrimitive.Root alt="Zach Nugent's Avatar">
  <AvatarPrimitive.Image source={{ uri: GITHUB_AVATAR_URI }} />
  <AvatarPrimitive.Fallback>
    <Text>ZN</Text>
  </AvatarPrimitive.Fallback>
</AvatarPrimitive.Root>;
```

## Props

### Root

Extends `View` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| alt\*   | string  |              |
| asChild | boolean | _(optional)_ |

### Image

Extends `Image` props (except `alt`)

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Fallback

Extends `View` props

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |
