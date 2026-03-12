---
name: react-native-reusables
description: "Build universal React Native component libraries with shadcn/ui patterns using RN Primitives and NativeWind. WHEN: \"shadcn React Native\", \"RN Primitives\", \"react-native-reusables\", \"mobile UI components\", \"Expo components\", \"universal components\"."
---

## Core Principles

React Native Reusables (RNR) adapts the **shadcn/ui** philosophy to mobile-first constraints using **RN Primitives** — a universal port of Radix UI with near-identical APIs.

- **Portal Requirement**: Overlay components (Dialog, AlertDialog, Popover, Select, DropdownMenu, ContextMenu, HoverCard, Tooltip, Menubar, NavigationMenu, Toast) **require** `<PortalHost />` as the last child of the app root (`app/_layout.tsx`).
- **No Cascading Styles**: `Text` does not inherit styles from parent views — style each element directly.
- **Shared Dependencies**: Most components depend on the `Types`, `Hooks`, and `Slot` primitives.
- **Platform Files**: Universal components use `.web.tsx` (Radix-backed) and `.tsx` (RN Primitives native).
- **Programmatic Control**: Trigger refs (e.g., `DropdownMenuTriggerRef`, `SelectTriggerRef`) expose `open()` / `close()` methods for imperative control.

## Mobile-Specific Warnings

| Component | Warning |
|-----------|---------|
| **Slider** | Gesture handling must be implemented manually on native |
| **Toast** | Auto-dismiss timer must be implemented manually |
| **ContextMenu** | Triggered by long-press on native, right-click on web |
| **Menubar** | Must manually handle closing when navigating away from the screen |
| **NavigationMenu** | Must manually handle closing when navigating away from the screen |
| **Tooltip** | `side` only supports `'top'` / `'bottom'` on native (`'left'`/`'right'` are web-only) |
| **Label** | Must use `nativeID` on `Label.Text`; match with `aria-labelledby` on the form field |

## Implementation Workflow

1. Install the component: `npx expo install @rn-primitives/<component>`
2. Install peer dependencies if needed: `npx expo install @rn-primitives/portal`
3. For Portal-based components, add `<PortalHost />` to root layout
4. Read the component's reference file for full prop tables and context hooks

## Reference Files

All 33 primitives have a dedicated reference. Read the relevant file before implementing a component.

**Core UI Primitives**

| Component | Portal |
|-----------|--------|
| [Accordion](references/accordion.md) | No |
| [Alert Dialog](references/alert-dialog.md) | Yes |
| [Aspect Ratio](references/aspect-ratio.md) | No |
| [Avatar](references/avatar.md) | No |
| [Checkbox](references/checkbox.md) | No |
| [Collapsible](references/collapsible.md) | No |
| [Context Menu](references/context-menu/README.md) | Yes |
| [Dialog](references/dialog.md) | Yes |
| [Dropdown Menu](references/dropdown-menu/README.md) | Yes |
| [Hover Card](references/hover-card.md) | Yes |
| [Label](references/label.md) | No |
| [Menubar](references/menubar/README.md) | Yes |
| [Navigation Menu](references/navigation-menu.md) | Yes |
| [Popover](references/popover.md) | Yes |
| [Progress](references/progress.md) | No |
| [Radio Group](references/radio-group.md) | No |
| [Select](references/select.md) | Yes |
| [Separator](references/separator.md) | No |
| [Slider](references/slider.md) | No |
| [Switch](references/switch.md) | No |
| [Table](references/table.md) | No |
| [Tabs](references/tabs.md) | No |
| [Toast](references/toast.md) | Yes |
| [Toggle](references/toggle.md) | No |
| [Toggle Group](references/toggle-group.md) | No |
| [Toolbar](references/toolbar.md) | No |
| [Tooltip](references/tooltip.md) | Yes |

**Shared Primitives**

| Component | Description |
|-----------|-------------|
| [Hooks](references/hooks.md) | `useAugmentedRef`, `useControllableState`, `useRelativePosition` |
| [Portal](references/portal.md) | Native portal implementation backed by zustand |
| [Slot](references/slot.md) | Merges props onto immediate child; enables `asChild` pattern |
| [Types](references/types.md) | Shared TypeScript types |
| [Utils](references/utils.md) | `ToggleGroupUtils`, `EmptyGestureResponderEvent` |
| [Index](references/index.md) | Full component listing |
