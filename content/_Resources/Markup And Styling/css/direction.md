direction
=========

**Warning:** Where possible, authors are encouraged to avoid using the
`direction` CSS property and use the HTML
[`dir`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#dir)
global attribute instead.

The `direction` CSS property sets the direction of text, table columns,
and horizontal overflow. Use `rtl` for languages written from right to
left (like Hebrew or Arabic), and `ltr` for those written from left to
right (like English and most other languages).

Try it
------

Note that text direction is usually defined within a document (e.g.,
with [HTML\'s `dir`
attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir))
rather than through direct use of the `direction` property.

The property sets the base text direction of block-level elements and
the direction of embeddings created by the
[`unicode-bidi`](unicode-bidi.md) property. It also sets the default
alignment of text, block-level elements, and the direction that cells
flow within a table row.

Unlike the `dir` attribute in HTML, the `direction` property is not
inherited from table columns into table cells, since CSS inheritance
follows the document tree, and table cells are inside of rows but not
inside of columns.

The `direction` and [`unicode-bidi`](unicode-bidi.md) properties are the
two only properties which are not affected by the [`all`](all.md) shorthand
property.

Syntax
------

[css]

```css
/* Keyword values */
direction: ltr;
direction: rtl;

/* Global values */
direction: inherit;
direction: initial;
direction: revert;
direction: revert-layer;
direction: unset;
```

### Values

[`ltr`](#ltr)

:   Text and other elements go from left to right. This is the default
    value.

[`rtl`](#rtl)

:   Text and other elements go from right to left.

For the `direction` property to have any effect on inline-level
elements, the [`unicode-bidi`](unicode-bidi.md) property\'s value must be
`embed` or `override`.

Formal definition
-----------------

  ---------------------------------- ----------------
  [Initial value](initial_value.md)     `ltr`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     Not animatable
  ---------------------------------- ----------------

Formal syntax
-------------

```
direction = 
  ltr  |
  rtl  
```

Examples
--------

### Setting right-to-left direction

In the example below are two strings of text, both which are displaying
using `direction: rtl`. While the Arabic text is displayed correctly
with this setting, the English text now has a full stop in an unusual
location.

[css]

```css
blockquote {
  direction: rtl;
  width: 300px;
}
```

[html]

```html
<blockquote>
  <p>This paragraph is in English but incorrectly goes right to left.</p>
  <p></p>
</blockquote>

<blockquote>
  <p>هذه الفقرة باللغة العربية ، لذا يجب الانتقال من اليمين إلى اليسار.</p>
  <p></p>
</blockquote>
```

Specifications
--------------

  ----------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------

  [CSS Writing Modes Level 4\
  [\#
  direction]](https://drafts.csswg.org/css-writing-modes/#direction)

  ----------------------------------------------------------------------------

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

`direction`

2

12

1

5.5

9.2

1

4.4

18

4

10.1

1

1.0

See also
--------

- [`unicode-bidi`](unicode-bidi.md)
- [`writing-mode`](writing-mode.md)
- The HTML
    [`dir`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#dir)
    global attribute

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/direction>
