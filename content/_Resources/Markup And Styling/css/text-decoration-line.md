text-decoration-line
====================

The `text-decoration-line`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the kind of decoration that is used on text in an element, such as an
underline or overline.

Try it
------

When setting multiple line-decoration properties at once, it may be more
convenient to use the [`text-decoration`](text-decoration.md) shorthand
property instead.

Syntax
------

[css]

```css
/* Single keyword */
text-decoration-line: none;
text-decoration-line: underline;
text-decoration-line: overline;
text-decoration-line: line-through;
text-decoration-line: blink;

/* Multiple keywords */
text-decoration-line: underline overline; /* Two decoration lines */
text-decoration-line: overline underline line-through; /* Multiple decoration lines */

/* Global values */
text-decoration-line: inherit;
text-decoration-line: initial;
text-decoration-line: revert;
text-decoration-line: revert-layer;
text-decoration-line: unset;
```

The `text-decoration-line` property is specified as `none`, or **one or
more** space-separated values from the list below.

### Values

[`none`](#none)

:   Produces no text decoration.

[`underline`](#underline)

:   Each line of text has a decorative line beneath it.

[`overline`](#overline)

:   Each line of text has a decorative line above it.

[`line-through`](#line-through)

:   Each line of text has a decorative line going through its middle.

[`blink`](#blink) [Deprecated]

:   The text blinks (alternates between visible and invisible).
    Conforming user agents may not blink the text. This value is
    **deprecated** in favor of [CSS animations](animation.md).

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
text-decoration-line = 
  none                                                |
  [ underline || overline || line-through || blink ]  
```

Examples
--------

### Basic example

[html]

```html
<p class="wavy">Here's some text with wavy red underline!</p>
<p class="both">This text has lines both above and below it.</p>
```

[css]

```css
.wavy {
  text-decoration-line: underline;
  text-decoration-style: wavy;
  text-decoration-color: red;
}

.both {
  text-decoration-line: underline overline;
}
```

Specifications
--------------

  -----------------------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------------------

  [CSS Text Decoration Module Level 3\
  [\#
  text-decoration-line-property]](https://drafts.csswg.org/css-text-decor/#text-decoration-line-property)

  -----------------------------------------------------------------------------------------------------------------

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

`text-decoration-line`

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

`blink`

57The `blink` value does not have any effect.

79The `blink` value does not have any effect.

26The `blink` value does not have any effect.

No

44

8

57The `blink` value does not have any effect.

57The `blink` value does not have any effect.

26The `blink` value does not have any effect.

43

8

7.0The `blink` value does not have any effect.

See also
--------

- When setting multiple line-decoration properties at once, it may be
    more convenient to use the [`text-decoration`](text-decoration.md)
    shorthand property instead, which also includes:
  - [`text-decoration-style`](text-decoration-style.md)
  - [`text-decoration-color`](text-decoration-color.md)
  - [`text-decoration-thickness`](text-decoration-thickness.md)
- [`text-underline-offset`](text-underline-offset.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-line>
