text-emphasis
=============

The `text-emphasis`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property applies
emphasis marks to text (except spaces and control characters). It is a
[shorthand](shorthand_properties.md) for
[`text-emphasis-style`](text-emphasis-style.md) and
[`text-emphasis-color`](text-emphasis-color.md).

Try it
------

The `text-emphasis` property is quite different from
[`text-decoration`](text-decoration.md). The `text-decoration` property
does not inherit, and the decoration specified is applied across the
whole element. However, text-emphasis does inherit, which means it is
possible to change emphasis marks for descendants.

The size of the emphasis symbol, like ruby symbols, is about 50% of the
size of the font, and `text-emphasis` may affect line height when the
current leading is not enough for the marks.

**Note:** `text-emphasis` doesn\'t reset the value of
[`text-emphasis-position`](text-emphasis-position.md). This is because if
the style and the color of emphasis marks may vary in a text, it is
extremely unlikely that their position will. In the very rare cases when
this is needed, use the property
[`text-emphasis-position`](text-emphasis-position.md).

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`text-emphasis-color`](text-emphasis-color.md)
- [`text-emphasis-style`](text-emphasis-style.md)

Syntax
------

[css]

```css
/* Initial value */
text-emphasis: none; /* No emphasis marks */

/* <string> value */
text-emphasis: "x";
text-emphasis: "点";
text-emphasis: "\25B2";
text-emphasis: "*" #555;
text-emphasis: "foo"; /* Should NOT use. It may be computed to or rendered as 'f' only */

/* Keywords value */
text-emphasis: filled;
text-emphasis: open;
text-emphasis: filled sesame;
text-emphasis: open sesame;

/* Keywords value combined with a color */
text-emphasis: filled sesame #555;

/* Global values */
text-emphasis: inherit;
text-emphasis: initial;
text-emphasis: revert;
text-emphasis: revert-layer;
text-emphasis: unset;
```

### Values

[`none`](#none)

:   No emphasis marks.

[`filled`](#filled)

:   The shape is filled with solid color. If neither `filled` nor `open`
    is present, this is the default.

[`open`](#open)

:   The shape is hollow.

[`dot`](#dot)

:   Display small circles as marks. The filled dot is `'•'` (`U+2022`),
    and the open dot is `'◦'` (`U+25E6`).

[`circle`](#circle)

:   Display large circles as marks. The filled circle is `'●'`
    (`U+25CF`), and the open circle is `'○'` (`U+25CB`). This is the
    default shape in horizontal writing modes when no other shape is
    given.

[`double-circle`](#double-circle)

:   Display double circles as marks. The filled double-circle is `'◉'`
    (`U+25C9`), and the open double-circle is `'◎'` (`U+25CE`).

[`triangle`](#triangle)

:   Display triangles as marks. The filled triangle is `'▲'` (`U+25B2`),
    and the open triangle is `'△'` (`U+25B3`).

[`sesame`](#sesame)

:   Display sesames as marks. The filled sesame is `'﹅'` (`U+FE45`),
    and the open sesame is `'﹆'` (`U+FE46`). This is the default shape
    in vertical writing modes when no other shape is given.

[`<string>`](#string)

:   Display the given string as marks. Authors should not specify more
    than one *character* in `<string>`. The UA may truncate or ignore
    strings consisting of more than one grapheme cluster.

[`<color>`](#color)

:   Defines the color of the mark. If no color is present, it defaults
    to `currentcolor`.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](text-emphasis-style.md): |
|                                   |     `none`                        |
|                                   | -   [](text-emphasis-color.md): |
|                                   |     `currentcolor`                |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements                      |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | yes                               |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](text-emphasis-style.md): |
|                                   |     as specified                  |
|                                   | -   [](text-emphasis-color.md): |
|                                   |     computed color                |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](text-emphasis-color.md): |
|                                   |     a                             |
|                                   |     [](color_value.md#interpolation) |
|                                   | -   [](text-emphasis-style.md): |
|                                   |     discrete                      |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
text-emphasis = 
  <'text-emphasis-style'>  ||
  <'text-emphasis-color'>  
```

Examples
--------

### A heading with emphasis shape and color

This example draws a heading with triangles used to emphasize each
character.

#### CSS

[css]

```css
h2 {
  text-emphasis: triangle #d55;
}
```

#### HTML

[html]

```html
<h2>This is important!</h2>
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------

  [CSS Text Decoration Module Level 3\
  [\#
  text-emphasis-property]](https://drafts.csswg.org/css-text-decor/#text-emphasis-property)

  ---------------------------------------------------------------------------------------------------

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

`text-emphasis`

9925

9979

46

No

8515

77

994.4

9925

46

6814

77

18.01.5

See also
--------

- The longhand properties
    [`text-emphasis-style`](text-emphasis-style.md),
    [`text-emphasis-color`](text-emphasis-color.md).
- The [`text-emphasis-position`](text-emphasis-position.md) property
    allowing to define the position of the emphasis marks.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis>
