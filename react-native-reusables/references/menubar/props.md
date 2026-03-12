# Menubar Props

## Root

Extends `View` props

| Prop | Type | Note |
|------|------|------|
| value\* | string \| undefined | |
| onValueChange\* | (value: string \| undefined) => void | |
| asChild | boolean | _(optional)_ |

## Menu

Extends `View` props — `value*: string`, `asChild?: boolean`

## Trigger

Extends `Pressable` props — `asChild?: boolean`

## Portal

| Prop | Type | Note |
|------|------|------|
| children\* | React.ReactNode | |
| forceMount | true \| undefined | _(optional)_ |
| hostName | string | **Web only** _(optional)_ |
| container | HTMLElement \| null \| undefined | **Web only** _(optional)_ |

## Overlay

Extends `Pressable` props — `asChild?: boolean`, `forceMount?: true \| undefined`

## Content

Extends `View` props

| Prop | Type | Note |
|------|------|------|
| asChild | boolean | _(optional)_ |
| forceMount | true \| undefined | _(optional)_ |
| alignOffset | number | _(optional)_ |
| insets | Insets | _(optional)_ |
| avoidCollisions | boolean | _(optional)_ |
| align | 'start' \| 'center' \| 'end' | _(optional)_ |
| side | 'top' \| 'bottom' | _(optional)_ |
| sideOffset | number | _(optional)_ |
| disablePositioningStyle | boolean | **Native only** _(optional)_ |
| loop | boolean | **Web only** _(optional)_ |
| onCloseAutoFocus | (event: Event) => void | **Web only** _(optional)_ |
| onEscapeKeyDown | (event: KeyboardEvent) => void | **Web only** _(optional)_ |
| onPointerDownOutside | (event: PointerDownOutsideEvent) => void | **Web only** _(optional)_ |
| onFocusOutside | (event: FocusOutsideEvent) => void | **Web only** _(optional)_ |
| onInteractOutside | PointerDownOutsideEvent \| FocusOutsideEvent | **Web only** _(optional)_ |
| collisionBoundary | Element \| null \| Array\<Element \| null> | **Web only** _(optional)_ |
| sticky | 'partial' \| 'always' | **Web only** _(optional)_ |
| hideWhenDetached | boolean | **Web only** _(optional)_ |

## Item / Group / Label / Separator

- **Group** extends `Text` — `asChild?: boolean`
- **Label** extends `Text` — `asChild?: boolean`
- **Item** extends `Pressable` — `asChild?: boolean`, `textValue?: string`, `closeOnPress?: boolean`
- **Separator** extends `View` — `asChild?: boolean`, `decorative?: boolean`

## CheckboxItem

Extends `Pressable` — `checked*: boolean`, `onCheckedChange*: (value: boolean) => void`, `textValue*: string`, `asChild?: boolean`, `closeOnPress?: boolean` (Native only)

## RadioGroup / RadioItem

- **RadioGroup** extends `View` — `value*: string`, `onValueChange*: (value: string) => void`, `asChild?: boolean`
- **RadioItem** extends `Pressable` — `value*: string`, `onCheckedChange*: (value: boolean) => void`, `asChild?: boolean`, `closeOnPress?: boolean` (Native only)

## ItemIndicator

Extends `View` — `asChild?: boolean`, `forceMount?: true | undefined`

## Sub / SubTrigger / SubContent

- **Sub** extends `View` — `asChild?: boolean`, `defaultOpen?: boolean`, `open?: boolean`, `onOpenChange?: (value: boolean) => void`
- **SubTrigger** extends `Pressable` — `textValue?: string`, `asChild?: boolean`
- **SubContent** extends `Pressable` — `asChild?: boolean`, `forceMount?: true | undefined`
