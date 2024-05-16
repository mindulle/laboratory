column-rule
===========

The `column-rule` [shorthand](shorthand_properties.md)
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the width, style, and color of the line drawn between columns in a
multi-column layout.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`column-rule-color`](column-rule-color.md)
- [`column-rule-style`](column-rule-style.md)
- [`column-rule-width`](column-rule-width.md)

Syntax
------

[css]

```css
column-rule: dotted;
column-rule: solid 8px;
column-rule: solid blue;
column-rule: thick inset blue;

/* Global values */
column-rule: inherit;
column-rule: initial;
column-rule: revert;
column-rule: revert-layer;
column-rule: unset;
```

### Values

The `column-rule` property is specified as one, two, or three of the
values listed below, in any order.

[`<'column-rule-width'>`](#column-rule-width)

:   Is a [`<length>`](length.md) or one of the three keywords, `thin`,
    `medium`, or `thick`. See [`border-width`](border-width.md) for
    details.

[`<'column-rule-style'>`](#column-rule-style)

:   See [`border-style`](border-style.md) for possible values and details.

[`<'column-rule-color'>`](#column-rule-color)

:   Is a [`<color>`](color_value.md) value.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](column-rule-width.md): |
|                                   |     `medium`                      |
|                                   | -   [](column-rule-style.md): |
|                                   |     `none`                        |
|                                   | -   [](column-rule-color.md): |
|                                   |     `currentcolor`                |
+-----------------------------------+-----------------------------------+
| Applies to                        | multicol elements                 |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](column-rule-color.md): |
|                                   |     computed color                |
|                                   | -   [](column-rule-style.md): |
|                                   |     as specified                  |
|                                   | -   [](column-rule-width.md): |
|                                   |     the absolute length; `0` if   |
|                                   |     the                           |
|                                   |     [](column-rule-style.md) |
|                                   |     is `none` or `hidden`         |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](column-rule-color.md): |
|                                   |     a                             |
|                                   |     [](color_value.md#interpolation) |
|                                   | -   [](column-rule-style.md): |
|                                   |     discrete                      |
|                                   | -   [](column-rule-width.md): |
|                                   |     a                             |
|                                   |                                   |
|                                   |    [length](length.md#interpolation) |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
column-rule = 
  <'column-rule-width'>  ||
  <'column-rule-style'>  ||
  <'column-rule-color'>  
```

Examples
--------

### Example 1

[css]

```css
/* Same as "medium dotted currentcolor" */
p.foo {
  column-rule: dotted;
}

/* Same as "medium solid blue" */
p.bar {
  column-rule: solid blue;
}

/* Same as "8px solid currentcolor" */
p.baz {
  column-rule: solid 8px;
}

p.abc {
  column-rule: thick inset blue;
}
```

### Example 2

#### HTML

[html]

```html
<p class="content-box">
  This is a bunch of text split into three columns. Take note of how the
  `column-rule` property is used to adjust the style, width, and color of the
  rule that appears between the columns.
</p>
```

#### CSS

[css]

```css
.content-box {
  padding: 0.3em;
  background: #ff7;
  column-count: 3;
  column-rule: inset 2px #33f;
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------

  [CSS Multi-column Layout Module Level 1\
  [\#
  column-rule]](https://drafts.csswg.org/css-multicol/#column-rule)

  ---------------------------------------------------------------------------

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

`column-rule`

501

1212

52

3.5--74Before Firefox 3, the default value for the `normal` keyword was
`0` and not `1em`.

10

1511.1

93

50≤37

5018

524

1411.1

91

5.01.0

See also
--------

- [Multiple-column
    Layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout)
- [`column-rule-style`](column-rule-style.md)
- [`column-rule-width`](column-rule-width.md)
- [`column-rule-color`](column-rule-color.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule>
