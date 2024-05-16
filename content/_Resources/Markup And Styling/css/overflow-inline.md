overflow-inline
===============

The `overflow-inline`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
what shows when content overflows the inline start and end edges of a
box. This may be nothing, a scroll bar, or the overflow content.

**Note:** The `overflow-inline` property maps to
[`overflow-y`](overflow-y.md) or [`overflow-x`](overflow-x.md) depending on
the writing mode of the document.

Syntax
------

[css]

```css
/* Keyword values */
overflow-inline: visible;
overflow-inline: hidden;
overflow-inline: clip;
overflow-inline: scroll;
overflow-inline: auto;

/* Global values */
overflow-inline: inherit;
overflow-inline: initial;
overflow-inline: revert;
overflow-inline: revert-layer;
overflow-inline: unset;
```

The `overflow-inline` property is specified as a single
[`<overflow>`](overflow_value.md) keyword value.

### Values

[`visible`](#visible)

:   Content is not clipped and may be rendered outside the padding
    box\'s inline start and end edges.

[`hidden`](#hidden)

:   Content is clipped if necessary to fit the inline dimension in the
    padding box. No scrollbars are provided.

[`clip`](#clip)

:   Overflow content is clipped at the element\'s overflow clip edge
    that is defined using the
    [`overflow-clip-margin`](overflow-clip-margin.md) property.

[`scroll`](#scroll)

:   Content is clipped if necessary to fit in the padding box in the
    inline dimension. Browsers display scrollbars whether or not any
    content is actually clipped. (This prevents scrollbars from
    appearing or disappearing when the content changes.) Printers may
    still print overflowing content.

[`auto`](#auto)

:   Depends on the user agent. If content fits inside the padding box,
    it looks the same as `visible`, but still establishes a new
    block-formatting context. Desktop browsers provide scrollbars if
    content overflows.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         Block-containers, flex containers, and grid containers
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified, except with `visible`/`clip` computing to `auto`/`hidden` respectively if one of [`overflow-x`](overflow-x.md) or [`overflow-y`](overflow-y.md) is neither `visible` nor clip
  Animation type                     discrete
  ---------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
overflow-inline = 
  <'overflow'>  
```

Examples
--------

### Setting inline overflow behavior

#### HTML

[html]

```html
<ul>
  <li>
    <code>overflow-inline: hidden</code> (hides the text outside the box)
    <div id="div1">ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ</div>
  </li>

  <li>
    <code>overflow-inline: scroll</code> (always adds a scrollbar)
    <div id="div2">ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ</div>
  </li>

  <li>
    <code>overflow-inline: visible</code> (displays the text outside the box if
    needed)
    <div id="div3">ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ</div>
  </li>

  <li>
    <code>overflow-inline: auto</code> (equivalent to <code>scroll</code>
    in most browsers)
    <div id="div4">ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ</div>
  </li>

  <li>
    <code>overflow-inline: clip</code> (hides the text outside the box beyond
    the overflow clip edge)
    <code>clip</code>
    <div id="div5">ABCDEFGHIJKLMOPQRSTUVWXYZABCDEFGHIJKLMOPQRSTUVWXYZ</div>
  </li>
</ul>
```

#### CSS

[css]

```css
div {
  border: 1px solid black;
  width: 250px;
  margin-bottom: 12px;
}

#div1 {
  overflow-inline: hidden;
}
#div2 {
  overflow-inline: scroll;
}
#div3 {
  overflow-inline: visible;
}
#div4 {
  overflow-inline: auto;
}
#div5 {
  overflow-inline: clip;
  overflow-clip-margin: 2em;
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------

  [CSS Overflow Module Level 3\
  [\#
  overflow-control]](https://drafts.csswg.org/css-overflow/#overflow-control)

  -------------------------------------------------------------------------------------

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

`overflow-inline`

No

No

69

No

No

No

No

No

79

No

No

No

See also
--------

- [`clip`](clip.md), [`display`](display.md), [`overflow`](overflow.md),
    [`overflow-block`](_Resources/Markup%20And%20Styling/css/overflow-block.md),
    [`overflow-clip-margin`](overflow-clip-margin.md),
    [`overflow-x`](overflow-x.md), [`overflow-y`](overflow-y.md),
    [`text-overflow`](text-overflow.md), [`white-space`](white-space.md)
- [CSS overflow](css_overflow.md) module
- [CSS logical properties](css_logical_properties_and_values.md)
- [CSS writing modes](css_writing_modes.md)
- [CSS building blocks: Overflowing
    content](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Overflowing_content)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-inline>
