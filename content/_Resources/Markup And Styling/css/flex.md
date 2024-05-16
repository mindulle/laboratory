flex
====

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `flex` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[shorthand property](shorthand_properties.md) sets how a flex *item* will
grow or shrink to fit the space available in its flex container.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`flex-grow`](flex-grow.md)
- [`flex-shrink`](flex-shrink.md)
- [`flex-basis`](flex-basis.md)

Syntax
------

[css]

```css
/* Keyword values */
flex: auto;
flex: initial;
flex: none;

/* One value, unitless number: flex-grow
flex-basis is then equal to 0. */
flex: 2;

/* One value, width/height: flex-basis */
flex: 10em;
flex: 30%;
flex: min-content;

/* Two values: flex-grow | flex-basis */
flex: 1 30px;

/* Two values: flex-grow | flex-shrink */
flex: 2 2;

/* Three values: flex-grow | flex-shrink | flex-basis */
flex: 2 2 10%;

/* Global values */
flex: inherit;
flex: initial;
flex: revert;
flex: revert-layer;
flex: unset;
```

The `flex` property may be specified using one, two, or three values.

- **One-value syntax:** the value must be one of:
  - a valid value for [`<flex-grow>`](flex-grow.md): then the shorthand
        expands to `flex: <flex-grow> 1 0`.
  - a valid value for [`<flex-basis>`](flex-basis.md): then the
        shorthand expands to `flex: 1 1 <flex-basis>`.
  - the keyword `none` or one of the global keywords.
- **Two-value syntax:**
  - The first value must be a valid value for
        [`flex-grow`](flex-grow.md).
  - The second value must be one of:
    - a valid value for [`flex-shrink`](flex-shrink.md): then the
            shorthand expands to `flex: <flex-grow> <flex-shrink> 0`.
    - a valid value for [`flex-basis`](flex-basis.md): then the
            shorthand expands to `flex: <flex-grow> 1 <flex-basis>`.
- **Three-value syntax:** the values must be in the following order:
    1. a valid value for [`flex-grow`](flex-grow.md).
    2. a valid value for [`flex-shrink`](flex-shrink.md).
    3. a valid value for [`flex-basis`](flex-basis.md).

### Values

[`initial`](#initial)

:   The item is sized according to its `width` and `height` properties.
    It shrinks to its minimum size to fit the container, but does not
    grow to absorb any extra free space in the flex container. This is
    equivalent to setting \"`flex: 0 1 auto`\".

[`auto`](#auto)

:   The item is sized according to its `width` and `height` properties,
    but grows to absorb any extra free space in the flex container, and
    shrinks to its minimum size to fit the container. This is equivalent
    to setting \"`flex: 1 1 auto`\".

[`none`](#none)

:   The item is sized according to its `width` and `height` properties.
    It is fully inflexible: it neither shrinks nor grows in relation to
    the flex container. This is equivalent to setting
    \"`flex: 0 0 auto`\".

[`<'flex-grow'>`](#flex-grow)

:   Defines the [`flex-grow`](flex-grow.md) of the flex item. Negative
    values are considered invalid. Defaults to `1` when omitted.
    (initial is `0`)

[`<'flex-shrink'>`](#flex-shrink)

:   Defines the [`flex-shrink`](flex-shrink.md) of the flex item. Negative
    values are considered invalid. Defaults to `1` when omitted.
    (initial is `1`)

[`<'flex-basis'>`](#flex-basis)

:   Defines the [`flex-basis`](flex-basis.md) of the flex item. A preferred
    size of `0` must have a unit to avoid being interpreted as a
    flexibility. Defaults to `0` when omitted. (initial is `auto`)

Description
-----------

For most purposes, authors should set `flex` to one of the following
values: `auto`, `initial`, `none`, or a positive unitless number. To see
the effect of these values, try resizing the flex containers below:

By default flex items don\'t shrink below their minimum content size. To
change this, set the item\'s [`min-width`](min-width.md) or
[`min-height`](min-height.md).

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [`flex-grow`](flex-grow.md): `0` |
|                                   | -   [`flex-shrink`](flex-shrink.md): |
|                                   |     `1`                           |
|                                   | -   [`flex-basis`](flex-basis.md):   |
|                                   |     `auto`                        |
+-----------------------------------+-----------------------------------+
| Applies to                        | flex items, including in-flow     |
|                                   | pseudo-elements                   |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [`flex-grow`](flex-grow.md): as  |
|                                   |     specified                     |
|                                   | -   [`flex-shrink`](flex-shrink.md): |
|                                   |     as specified                  |
|                                   | -   [`flex-basis`](flex-basis.md):   |
|                                   |     as specified, but with        |
|                                   |     relative lengths converted    |
|                                   |     into absolute lengths         |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [`flex-grow`](flex-grow.md): a   |
|                                   |                                   |
|                                   |    [number](number.md#interpolation) |
|                                   | -   [`flex-shrink`](flex-shrink.md): |
|                                   |     a                             |
|                                   |                                   |
|                                   |    [number](number.md#interpolation) |
|                                   | -   [`flex-basis`](flex-basis.md): a |
|                                   |                                   |
|                                   |   [length](length.md#interpolation), |
|                                   |     [](percentage.md#interpolation) |
|                                   |     or calc();                    |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
flex = 
  none                                                |
  [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]  
```

Examples
--------

### Setting flex: auto

This example shows how a flex item with `flex: auto` grows to absorb any
free space in the container.

#### HTML

[html]

```html
<div id="flex-container">
  <div id="flex-auto">flex: auto (click to toggle raw box)</div>
  <div id="flex-initial">flex: initial</div>
</div>
```

#### CSS

[css]

```css
#flex-container {
  display: flex;
  font-family: Consolas, Arial, sans-serif;
}

#flex-container > div {
  padding: 1rem;
}

#flex-auto {
  flex: auto;
  border: 1px solid #f00;
}

#flex-initial {
  border: 1px solid #000;
}
```

#### JavaScript

[js]

```js
const flexAuto = document.getElementById("flex-auto");
const flexInitial = document.getElementById("flex-initial");
flexAuto.addEventListener("click", () => {
  flexInitial.style.display =
    flexInitial.style.display === "none" ? "block" : "none";
});
```

#### Result

The flex container contains two flex items:

- \"flex: auto\" has a `flex` value of [`auto`](auto.md)
- \"flex: initial\" has a `flex` value of [`initial`](#initial)

The \"flex: initial\" item takes up as much space as its width requires,
but does not expand to take up any more space. All the remaining space
is taken up by \"flex: auto\".

When you click \"flex: auto\", we set \"flex: initial\"\'s
[`display`](display.md) property to `none`, removing it from the layout.
The \"flex: auto\" item then expands to occupy all the available space
in the container.

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [CSS Flexible Box Layout Module Level 1\
  [\#
  flex-property]](https://drafts.csswg.org/css-flexbox/#flex-property)

  ------------------------------------------------------------------------------

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`flex`

2921

1212

49

20\[\"Since Firefox 28, multi-line flexbox is supported.\", \"Before
Firefox 32, Firefox wasn\'t able to animate values starting or stopping
at `0`.\", \"Until Firefox 61, flex items that are sized according to
their content are sized using [`fit-content`, not
`max-content`](https://drafts.csswg.org/css-sizing-3/#column-sizing).\"\]

11\[\"Internet Explorer 11 ignores uses of
[`calc()`](https://developer.mozilla.org/docs/Web/CSS/calc) in the
`flex-basis` part of the `flex` syntax. This can be worked around by
using the longhand properties instead of the shorthand. See [Flexbug
\#8](https://github.com/philipwalton/flexbugs#8-flex-basis-doesnt-support-calc)
for more info.\", \"Internet Explorer 11 considers a unitless value in
the `flex-basis` part to be syntactically invalid (and will thus be
ignored). A workaround is to always include a unit in the `flex-basis`
part of the `flex` shorthand value. See [Flexbug
\#4](https://github.com/philipwalton/flexbugs#4-flex-shorthand-declarations-with-unitless-flex-basis-values-are-ignored)
for more info.\"\]

10\[\"Internet Explorer 10 and 11 ignore uses of
[`calc()`](https://developer.mozilla.org/docs/Web/CSS/calc) in the
`flex-basis` part of the `flex` syntax. This can be worked around by
using the longhand properties instead of the shorthand. See [Flexbug
\#8](https://github.com/philipwalton/flexbugs#8-flex-basis-doesnt-support-calc)
for more info.\", \"Internet Explorer 10 and 11 consider a unitless
value in the `flex-basis` part to be syntactically invalid (and will
thus be ignored). A workaround is to always include a unit in the
`flex-basis` part of the `flex` shorthand value. See [Flexbug
\#4](https://github.com/philipwalton/flexbugs#4-flex-shorthand-declarations-with-unitless-flex-basis-values-are-ignored)
for more info.\"\]

12.1

97

≤374.4

2925

49

20\[\"Since Firefox 28, multi-line flexbox is supported.\", \"Before
Firefox 32, Firefox wasn\'t able to animate values starting or stopping
at `0`.\", \"Until Firefox 61, flex items that are sized according to
their content are sized using [fit-content, not
max-content](https://drafts.csswg.org/css-sizing-3/#column-sizing).\"\]

12.1

97

2.01.5

See also
--------

- CSS Flexbox Guide: *[](basic_concepts_of_flexbox.md)*
- CSS Flexbox Guide: *[](controlling_ratios_of_flex_items_along_the_main_axis.md)*

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/flex>
