text-decoration-style
=====================

The `text-decoration-style`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the style of the lines specified by
[`text-decoration-line`](text-decoration-line.md). The style applies to all
lines that are set with `text-decoration-line`.

Try it
------

If the specified decoration has a specific semantic meaning, like a
line-through line meaning that some text has been deleted, authors are
encouraged to denote this meaning using an HTML tag, like
[`<del>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/del)
or [`<s>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/s).
As browsers can disable styling in some cases, the semantic meaning
won\'t disappear in such a situation.

When setting multiple line-decoration properties at once, it may be more
convenient to use the [`text-decoration`](text-decoration.md) shorthand
property instead.

Syntax
------

[css]

```css
/* Keyword values */
text-decoration-style: solid;
text-decoration-style: double;
text-decoration-style: dotted;
text-decoration-style: dashed;
text-decoration-style: wavy;

/* Global values */
text-decoration-style: inherit;
text-decoration-style: initial;
text-decoration-style: revert;
text-decoration-style: revert-layer;
text-decoration-style: unset;
```

### Values

[solid](#solid)

:   Draws a single line.

[double](#double)

:   Draws a double line.

[dotted](#dotted)

:   Draws a dotted line.

[dashed](#dashed)

:   Draws a dashed line.

[wavy](#wavy)

:   Draws a wavy line.

[-moz-none [Non-standard]](#-moz-none_non-standard)

:   Draws no line. Use
    [`text-decoration-line`](text-decoration-line.md)`: none` instead.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `solid`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
text-decoration-style = 
  solid   |
  double  |
  dotted  |
  dashed  |
  wavy    
```

Examples
--------

### Setting a wavy underline

The following creates a red wavy underline:

#### CSS

[css]

```css
.wavy {
  text-decoration-line: underline;
  text-decoration-style: wavy;
  text-decoration-color: red;
}
```

#### HTML

[html]

```html
<p class="wavy">This text has a wavy red line beneath it.</p>
```

#### Results

Specifications
--------------

  -------------------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------------------

  [CSS Text Decoration Module Level 3\
  [\#
  text-decoration-style-property]](https://drafts.csswg.org/css-text-decor/#text-decoration-style-property)

  -------------------------------------------------------------------------------------------------------------------

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

`text-decoration-style`

57

79

366--39

No

44

12.18

57

57

366--39

43

12.28

7.0

`wavy`

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

See also
--------

- When setting multiple line-decoration properties at once, it may be
    more convenient to use the [`text-decoration`](text-decoration.md)
    shorthand property instead.
- [`text-decoration-line`](text-decoration-line.md)
- [`text-decoration-color`](text-decoration-color.md)
- [`text-decoration-thickness`](text-decoration-thickness.md)
- [`text-underline-offset`](text-underline-offset.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-style>
