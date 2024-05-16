overflow-x
==========

The `overflow-x` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets what shows when content overflows a block-level element\'s
left and right edges. This may be nothing, a scroll bar, or the overflow
content. This property may also be set by using the
[`overflow`](overflow.md) shorthand property.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
overflow-x: visible;
overflow-x: hidden;
overflow-x: clip;
overflow-x: scroll;
overflow-x: auto;

/* Global values */
overflow-x: inherit;
overflow-x: initial;
overflow-x: revert;
overflow-x: revert-layer;
overflow-x: unset;
```

The `overflow-x` property is specified as a single
[`<overflow>`](overflow_value.md) keyword value.

If [`overflow-y`](overflow-y.md) is `hidden`, `scroll`, or `auto`, and the
`overflow-x` property is `visible` (default), the value will be
implicitly computed as `auto`.

### Values

[`visible`](#visible)

:   Overflow content is not clipped and may be visible outside the
    element\'s padding box on left and right edges. The element box is
    not a [scroll
    container](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container).

[`hidden`](#hidden)

:   Overflow content is clipped if necessary to fit horizontally in the
    elements\' padding box. No scroll bars are provided.

[`clip`](#clip)

:   Overflow content is clipped at the element\'s *overflow clip edge*
    that is defined using the
    [`overflow-clip-margin`](overflow-clip-margin.md) property. As a
    result, content overflows the element\'s padding box by the
    [`<length>`](length.md) value of `overflow-clip-margin` or by `0px` if
    not set. The difference between `clip` and `hidden` is that the
    `clip` keyword also forbids all scrolling, including programmatic
    scrolling. No new formatting context is created. To establish a
    formatting context, use `overflow: clip` along with
    [`display: flow-root`](display.md#flow-root). The element box is not a
    scroll container.

[`scroll`](#scroll)

:   Overflow content is clipped if necessary to fit horizontally inside
    the element\'s padding box. Browsers display scroll bars in the
    horizontal direction whether or not any content is actually clipped.
    (This prevents scroll bars from appearing or disappearing when the
    content changes.) Printers may still print overflowing content.

[`auto`](#auto)

:   Overflow content is clipped at the element\'s padding box, and
    overflow content can be scrolled into view. Unlike `scroll`, user
    agents display scroll bars *only if* the content is overflowing and
    hide scroll bars by default. If content fits inside the element\'s
    padding box, it looks the same as with `visible`, but still
    establishes a new block-formatting context. Desktop browsers provide
    scroll bars if content overflows.

**Note:** The keyword value `overlay` is a legacy value alias for
`auto`. With `overlay`, the scroll bars are drawn on top of the content
instead of taking up space.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `visible`
  Applies to                         Block-containers, flex containers, and grid containers
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified, except with `visible`/`clip` computing to `auto`/`hidden` respectively if one of [`overflow-x`](overflow-x.md) or [`overflow-y`](overflow-y.md) is neither `visible` nor clip
  Animation type                     discrete
  ---------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
overflow-x = 
  visible  |
  hidden   |
  clip     |
  scroll   |
  auto     
```

Examples
--------

### HTML

[html]

```html
<ul>
  <li>
    <code>overflow-x:hidden</code> — hides the text outside the box
    <div id="div1">ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ</div>
  </li>

  <li>
    <code>overflow-x:scroll</code> — always adds a scrollbar
    <div id="div2">ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ</div>
  </li>

  <li>
    <code>overflow-x:visible</code> — displays the text outside the box if
    needed
    <div id="div3">ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ</div>
  </li>

  <li>
    <code>overflow-x:auto</code> — on most browsers, equivalent to
    <code>scroll</code>
    <div id="div4">ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ</div>
  </li>
</ul>
```

### CSS

[css]

```css
#div1,
#div2,
#div3,
#div4 {
  border: 1px solid black;
  width: 250px;
  margin-bottom: 12px;
}

#div1 {
  overflow-x: hidden;
}
#div2 {
  overflow-x: scroll;
}
#div3 {
  overflow-x: visible;
}
#div4 {
  overflow-x: auto;
}
```

### Result

Specifications
--------------

  -------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------

  [CSS Overflow Module Level 3\
  [\#
  overflow-properties]](https://drafts.csswg.org/css-overflow/#overflow-properties)

  -------------------------------------------------------------------------------------------

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

`overflow-x`

1

12

3.5

85

9.5

3

4.4

18

4

14

1

1.0

`clip`

90

90

813.5--81

No

76

16

90

90

814--81

64

16

15.0

`overlay`

15

79

112

No

15

No

100

100

112

No

No

4.0

See also
--------

- [`clip`](clip.md), [`display`](display.md),
    [`text-overflow`](text-overflow.md), [`white-space`](white-space.md)
- [CSS overflow](css_overflow.md) module
- [CSS building blocks: Overflowing
    content](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Overflowing_content)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-x>
