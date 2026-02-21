# Aspect Ratio Primitive

Presents content within a chosen aspect ratio.

## Overview

Wraps content in a `View` that enforces a specific width-to-height ratio.

## Installation

```bash
npx expo install @rn-primitives/aspect-ratio
```

**Shared primitive dependencies (manual install):** Types, Slot

## Usage

```tsx
import * as AspectRatio from "@rn-primitives/aspect-ratio";

<AspectRatio.Root ratio={16 / 9} />;
```

## Props

### Root

Extends `View` props

| Prop  | Type   | Note                         |
| ----- | ------ | ---------------------------- |
| ratio | number | Defaults to `1` _(optional)_ |
