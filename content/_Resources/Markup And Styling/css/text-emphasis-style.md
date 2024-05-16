text-emphasis-style
===================

The `text-emphasis-style`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the appearance of emphasis marks. It can also be set, and reset, using
the [`text-emphasis`](text-emphasis.md) shorthand.

Try it
------

Syntax
------

[css]

```css
/* Initial value */
text-emphasis-style: none; /* No emphasis marks */

/* <string> values */
text-emphasis-style: "x";
text-emphasis-style: "点";
text-emphasis-style: "\25B2";
text-emphasis-style: "*";
text-emphasis-style: "foo"; /* Should NOT be used. It may be computed to or rendered as 'f' only */

/* Keyword values */
text-emphasis-style: filled;
text-emphasis-style: open;
text-emphasis-style: dot;
text-emphasis-style: circle;
text-emphasis-style: double-circle;
text-emphasis-style: triangle;
text-emphasis-style: filled sesame;
text-emphasis-style: open sesame;

/* Global values */
text-emphasis-style: inherit;
text-emphasis-style: initial;
text-emphasis-style: revert;
text-emphasis-style: revert-layer;
text-emphasis-style: unset;
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
    (`U+25CF`), and the open circle is `'○'` (`U+25CB`).

[`double-circle`](#double-circle)

:   Display double circles as marks. The filled double-circle is `'◉'`
    (`U+25C9`), and the open double-circle is `'◎'` (`U+25CE`).

[`triangle`](#triangle)

:   Display triangles as marks. The filled triangle is `'▲'` (`U+25B2`),
    and the open triangle is `'△'` (`U+25B3`).

[`sesame`](#sesame)

:   Display sesames as marks. The filled sesame is `'﹅'` (`U+FE45`),
    and the open sesame is `'﹆'` (`U+FE46`).

[`<string>`](#string)

:   Display the given string as marks. Authors should not specify more
    than one *character* in `<string>`. The UA may truncate or ignore
    strings consisting of more than one grapheme cluster.

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
text-emphasis-style = 
  none                                                |
  [ [ filled | open ] || [ dot | circle | double-circle | triangle | sesame ] ]  |
  <string>                                            
```

Examples
--------

### Basic example

[css]

```css
h2 {
  -webkit-text-emphasis-style: sesame;
  text-emphasis-style: sesame;
}
```

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------

  [CSS Text Decoration Module Level 3\
  [\#
  text-emphasis-style-property]](https://drafts.csswg.org/css-text-decor/#text-emphasis-style-property)

  ---------------------------------------------------------------------------------------------------------------

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

`text-emphasis-style`

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

- The related properties [`text-emphasis-color`](text-emphasis-color.md),
    [`text-emphasis`](text-emphasis.md).
- The [`text-emphasis-position`](text-emphasis-position.md) property
    allowing to define the position of the emphasis marks.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-style>
