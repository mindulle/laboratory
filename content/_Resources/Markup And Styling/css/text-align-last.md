text-align-last
===============

The `text-align-last` CSS property sets how the last line of a block or
a line, right before a forced line break, is aligned.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
text-align-last: auto;
text-align-last: start;
text-align-last: end;
text-align-last: left;
text-align-last: right;
text-align-last: center;
text-align-last: justify;

/* Global values */
text-align-last: inherit;
text-align-last: initial;
text-align-last: revert;
text-align-last: revert-layer;
text-align-last: unset;
```

### Values

[`auto`](#auto)

:   The affected line is aligned per the value of
    [`text-align`](text-align.md), unless [`text-align`](text-align.md) is
    `justify`, in which case the effect is the same as setting
    `text-align-last` to `start`.

[`start`](#start)

:   The same as `left` if direction is left-to-right and `right` if
    direction is right-to-left.

[`end`](#end)

:   The same as `right` if direction is left-to-right and `left` if
    direction is right-to-left.

[`left`](#left)

:   The inline contents are aligned to the left edge of the line box.

[`right`](#right)

:   The inline contents are aligned to the right edge of the line box.

[`center`](#center)

:   The inline contents are centered within the line box.

[`justify`](#justify)

:   The text is justified. Text should line up their left and right
    edges to the left and right content edges of the paragraph.

Formal definition
-----------------

  ---------------------------------- ------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         block containers
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ------------------

Formal syntax
-------------

```
text-align-last = 
  auto          |
  start         |
  end           |
  left          |
  right         |
  center        |
  justify       |
  match-parent  
```

Examples
--------

### Justifying the last line

#### CSS

[css]

```css
p {
  font-size: 1.4em;
  text-align: justify;
  text-align-last: center;
}
```

#### Results

Specifications
--------------

  -------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------

  [CSS Text Module Level 3\
  [\#
  text-align-last-property]](https://drafts.csswg.org/css-text/#text-align-last-property)

  -------------------------------------------------------------------------------------------------

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

`text-align-last`

47

12

4912--53

5.5\[\"IE only supports `text-align-last` when `text-align` is set to
`justify`.\", \"The `start` and `end` values are not supported.\"\]

34

16

47

47

4914--53

34

16

5.0

See also
--------

- [`text-align`](text-align.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-align-last>
