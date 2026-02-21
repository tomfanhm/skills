---
name: react-native-reusables
description: Specialized knowledge for building universal React Native component libraries with a shadcn/ui experience using RN Primitives and NativeWind. Use when creating, styling, or debugging UI components in an Expo or React Native environment. Trigger when the user mentions "shadcn React Native", "RN Primitives", "react-native-reusables", or specific primitives like Accordion, Dialog, Popover, Select, DropdownMenu, ContextMenu, Toast, Tooltip, Menubar, NavigationMenu, HoverCard, AlertDialog, Collapsible, Checkbox, Switch, RadioGroup, Slider, Tabs, Toggle, ToggleGroup, Toolbar, Table, Progress, Separator, AspectRatio, Avatar, Label, Portal, Slot in a mobile or universal app context.
---

## Core Principles

React Native Reusables (RNR) adapts the **shadcn/ui** philosophy to mobile-first constraints using **RN Primitives** — a universal port of Radix UI with near-identical APIs.

- **Portal Requirement**: Overlay components (Dialog, AlertDialog, Popover, Select, DropdownMenu, ContextMenu, HoverCard, Tooltip, Menubar, NavigationMenu, Toast) **require** `<PortalHost />` as the last child of the app root (`app/_layout.tsx`).
- **No Cascading Styles**: `Text` does not inherit styles from parent views — style each element directly.
- **Shared Dependencies**: Most components depend on the `Types`, `Hooks`, and `Slot` primitives.
- **Platform Files**: Universal components use `.web.tsx` (Radix-backed) and `.tsx` (RN Primitives native).
- **Programmatic Control**: Trigger refs (e.g., `DropdownMenuTriggerRef`, `SelectTriggerRef`) expose `open()` / `close()` methods for imperative control.

## Mobile-Specific Warnings

| Component          | Warning                                                                               |
| ------------------ | ------------------------------------------------------------------------------------- |
| **Slider**         | Gesture handling must be implemented manually on native                               |
| **Toast**          | Auto-dismiss timer must be implemented manually                                       |
| **ContextMenu**    | Triggered by long-press on native, right-click on web                                 |
| **Menubar**        | Must manually handle closing when navigating away from the screen                     |
| **NavigationMenu** | Must manually handle closing when navigating away from the screen                     |
| **Tooltip**        | `side` only supports `'top'` / `'bottom'` on native (`'left'`/`'right'` are web-only) |
| **Label**          | Must use `nativeID` on `Label.Text`; match with `aria-labelledby` on the form field   |

## Implementation Workflow

1. Install the component: `npx expo install @rn-primitives/<component>`
2. Install peer dependencies if needed: `npx expo install @rn-primitives/portal`
3. For Portal-based components, add `<PortalHost />` to root layout
4. Read the component's reference file from `references/` for full prop tables and context hooks

## Reference Files

All 33 primitives have a dedicated reference file in `references/`. Read the relevant file before implementing a component.

**Core UI Primitives**

| Reference File                  | Component                         |
| ------------------------------- | --------------------------------- |
| `references/accordion.md`       | Accordion                         |
| `references/alert-dialog.md`    | Alert Dialog — Portal required    |
| `references/aspect-ratio.md`    | Aspect Ratio                      |
| `references/avatar.md`          | Avatar                            |
| `references/checkbox.md`        | Checkbox                          |
| `references/collapsible.md`     | Collapsible                       |
| `references/context-menu.md`    | Context Menu — Portal required    |
| `references/dialog.md`          | Dialog — Portal required          |
| `references/dropdown-menu.md`   | Dropdown Menu — Portal required   |
| `references/hover-card.md`      | Hover Card — Portal required      |
| `references/label.md`           | Label                             |
| `references/menubar.md`         | Menubar — Portal required         |
| `references/navigation-menu.md` | Navigation Menu — Portal required |
| `references/popover.md`         | Popover — Portal required         |
| `references/progress.md`        | Progress                          |
| `references/radio-group.md`     | Radio Group                       |
| `references/select.md`          | Select — Portal required          |
| `references/separator.md`       | Separator                         |
| `references/slider.md`          | Slider                            |
| `references/switch.md`          | Switch                            |
| `references/table.md`           | Table                             |
| `references/tabs.md`            | Tabs                              |
| `references/toast.md`           | Toast — Portal required           |
| `references/toggle.md`          | Toggle                            |
| `references/toggle-group.md`    | Toggle Group                      |
| `references/toolbar.md`         | Toolbar                           |
| `references/tooltip.md`         | Tooltip — Portal required         |

**Shared Primitives**

| Reference File         | Component                                                                |
| ---------------------- | ------------------------------------------------------------------------ |
| `references/hooks.md`  | Hooks (`useAugmentedRef`, `useControllableState`, `useRelativePosition`) |
| `references/portal.md` | Portal — native portal implementation backed by zustand                  |
| `references/slot.md`   | Slot — merges props onto immediate child; enables `asChild` pattern      |
| `references/types.md`  | Types — shared TypeScript types                                          |
| `references/utils.md`  | Utils (`ToggleGroupUtils`, `EmptyGestureResponderEvent`)                 |
| `references/index.md`  | Full component listing                                                   |
