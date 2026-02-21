# Separator Primitive

Creates a visual or semantic distinction between content.

## Overview

A simple separator line supporting horizontal and vertical orientations.

## Installation

```bash
npx expo install @rn-primitives/separator
```

**Shared primitive dependencies (manual install):** Slot, Types

## Usage

```tsx
import * as SeparatorPrimitive from "@rn-primitives/separator";

<SeparatorPrimitive.Root />;
```

## Props

### Root

Extends `View` props

| Prop        | Type                       | Note                                  |
| ----------- | -------------------------- | ------------------------------------- |
| orientation | 'horizontal' \| 'vertical' | Defaults to `horizontal` _(optional)_ |
| decorative  | boolean                    | _(optional)_                          |
| asChild     | boolean                    | _(optional)_                          |
