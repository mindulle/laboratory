text-decoration
===============

The `text-decoration` [shorthand](shorthand_properties.md)
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the appearance of decorative lines on text. It is a shorthand for
[`text-decoration-line`](text-decoration-line.md),
[`text-decoration-color`](text-decoration-color.md),
[`text-decoration-style`](text-decoration-style.md), and the newer
[`text-decoration-thickness`](text-decoration-thickness.md) property.

Try it
------

Text decorations are drawn across descendant text elements. This means
that if an element specifies a text decoration, then a child element
can\'t remove the decoration. For example, in the markup
`<p>This text has <em>some emphasized words</em> in it.</p>`, the style
rule `p` would cause the entire
paragraph to be underlined. The style rule
`em` would not cause any change; the entire
paragraph would still be underlined. However, the rule
`em` would cause a second decoration to
appear on \"some emphasized words\".

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`text-decoration-color`](text-decoration-color.md)
- [`text-decoration-line`](text-decoration-line.md)
- [`text-decoration-style`](text-decoration-style.md)
- [`text-decoration-thickness`](text-decoration-thickness.md)

Syntax
------

[css]

```css
text-decoration: underline;
text-decoration: overline red;
text-decoration: none;

/* Global values */
text-decoration: inherit;
text-decoration: initial;
text-decoration: revert;
text-decoration: revert-layer;
text-decoration: unset;
```

The `text-decoration` property is specified as one or more
space-separated values representing the various longhand text-decoration
properties.

### Values

[`text-decoration-line`](text-decoration-line.md)

:   Sets the kind of decoration used, such as `underline` or
    `line-through`.

[`text-decoration-color`](text-decoration-color.md)

:   Sets the color of the decoration.

[`text-decoration-style`](text-decoration-style.md)

:   Sets the style of the line used for the decoration, such as `solid`,
    `wavy`, or `dashed`.

[`text-decoration-thickness`](text-decoration-thickness.md)

:   Sets the thickness of the line used for the decoration.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](text-decoration-color.md): |
|                                   |     `currentcolor`                |
|                                   | -   [](text-decoration-style.md): |
|                                   |     `solid`                       |
|                                   | -   [](text-decoration-line.md): |
|                                   |     `none`                        |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements. It also applies to  |
|                                   | [                                 |
|                                   | `::first-letter`](::first-letter) |
|                                   | and                               |
|                                   | [`::first-line`](::first-line).   |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](text-decoration-line.md): |
|                                   |     as specified                  |
|                                   | -   [](text-decoration-style.md): |
|                                   |     as specified                  |
|                                   | -   [](text-decoration-color.md): |
|                                   |     computed color                |
|                                   | -   [](text-decoration-thickness.md): |
|                                   |     as specified                  |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](text-decoration-color.md): |
|                                   |     a                             |
|                                   |     [](color_value.md#interpolation) |
|                                   | -   [](text-decoration-style.md): |
|                                   |     discrete                      |
|                                   | -   [](text-decoration-line.md): |
|                                   |     discrete                      |
|                                   | -   [](text-decoration-thickness.md): |
|                                   |     by computed value type        |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
text-decoration = 
  <'text-decoration-line'>   ||
  <'text-decoration-style'>  ||
  <'text-decoration-color'>  
```

Examples
--------

### Demonstration of text-decoration values

[css]

```css
.under {
  text-decoration: underline red;
}

.over {
  text-decoration: wavy overline lime;
}

.line {
  text-decoration: line-through;
}

.plain {
  text-decoration: none;
}

.underover {
  text-decoration: dashed underline overline;
}

.thick {
  text-decoration: solid underline purple 4px;
}

.blink {
  text-decoration: blink;
}
```

[html]

```html
<p class="under">This text has a line underneath it.</p>
<p class="over">This text has a line over it.</p>
<p class="line">This text has a line going through it.</p>
<p>
  This <a class="plain" href="#">link will not be underlined</a>, as links
  generally are by default. Be careful when removing the text decoration on
  anchors since users often depend on the underline to denote hyperlinks.
</p>
<p class="underover">This text has lines above <em>and</em> below it.</p>
<p class="thick">
  This text has a really thick purple underline in supporting browsers.
</p>
<p class="blink">
  This text might blink for you, depending on the browser you use.
</p>
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------

  [CSS Text Decoration Module Level 3\
  [\#
  text-decoration-property]](https://drafts.csswg.org/css-text-decor/#text-decoration-property)

  -------------------------------------------------------------------------------------------------------

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

`text-decoration`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

`shorthand`

57

79

6

No

44

8

57

57

6

43

8

7.0

`text-decoration-thickness`

87

87

70

No

73

No

87

87

79

62

No

14.0

See also
--------

- The individual text-decoration properties are
    [`text-decoration-line`](text-decoration-line.md),
    [`text-decoration-color`](text-decoration-color.md),
    [`text-decoration-style`](text-decoration-style.md), and
    [`text-decoration-thickness`](text-decoration-thickness.md).
- The [`text-decoration-skip-ink`](text-decoration-skip-ink.md),
    [`text-underline-offset`](text-underline-offset.md), and
    [`text-underline-position`](text-underline-position.md) properties also
    affect text-decoration, but are not included in the shorthand.
- The [`list-style`](list-style.md) attribute controls the appearance of
    items in HTML
    [`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol)
    and
    [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul)
    lists.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration>
