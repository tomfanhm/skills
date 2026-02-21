# Table Primitive

Shows an accessible table component.

## Overview

Semantic table structure with Header, Body, Footer, Row, Head, and Cell sub-components.

## Installation

```bash
npx expo install @rn-primitives/table
```

**Shared primitive dependencies (manual install):** Slot, Types

## Usage

```tsx
import * as TablePrimitive from "@rn-primitives/table";

<TablePrimitive.Root aria-labelledby="invoice-table">
  <TablePrimitive.Header>
    <TablePrimitive.Row>
      <TablePrimitive.Head>
        <Text>Invoice</Text>
      </TablePrimitive.Head>
      <TablePrimitive.Head>
        <Text>Status</Text>
      </TablePrimitive.Head>
      <TablePrimitive.Head>
        <Text>Amount</Text>
      </TablePrimitive.Head>
    </TablePrimitive.Row>
  </TablePrimitive.Header>
  <TablePrimitive.Body>
    <TablePrimitive.Row>
      <TablePrimitive.Cell>
        <Text>INV001</Text>
      </TablePrimitive.Cell>
      <TablePrimitive.Cell>
        <Text>Paid</Text>
      </TablePrimitive.Cell>
      <TablePrimitive.Cell>
        <Text>$250.00</Text>
      </TablePrimitive.Cell>
    </TablePrimitive.Row>
  </TablePrimitive.Body>
</TablePrimitive.Root>;
```

## Props

All sub-components extend `View` props and accept `asChild?: boolean`.

### Root

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Header

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Row

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Head

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Body

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Cell

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |

### Footer

| Prop    | Type    | Note         |
| ------- | ------- | ------------ |
| asChild | boolean | _(optional)_ |
