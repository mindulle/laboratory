fit-content
===========

The `fit-content` behaves as `fit-content(stretch)`. In practice this
means that the box will use the available space, but never more than
[`max-content`](max-content.md).

When used as laid out box size for [`width`](_Resources/Markup%20And%20Styling/css/width.md), [`height`](_Resources/Markup%20And%20Styling/css/height.md),
[`min-width`](min-width.md), [`min-height`](min-height.md),
[`max-width`](max-width.md) and [`max-height`](max-height.md) the maximum and
minimum sizes refer to the content size.

**Note:** The CSS Sizing specification also defines the
[`fit-content()`](fit-content_function.md) function. This page details the
keyword.

Syntax
------

[css]

```css
width: fit-content;
block-size: fit-content;
```

Examples
--------

### Using fit-content for box sizing

#### HTML

[html]

```html
<div class="container">
  <div class="item">Item</div>
  <div class="item">Item with more text in it.</div>
  <div class="item">
    Item with more text in it, hopefully we have added enough text so the text
    will start to wrap.
  </div>
</div>
```

#### CSS

[css]

```css
.container {
  border: 2px solid #ccc;
  padding: 10px;
  width: 20em;
}

.item {
  width: fit-content;
  background-color: #8ca0ff;
  padding: 5px;
  margin-bottom: 1em;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------

  [CSS Box Sizing Module Level 4\
  [\#
  valdef-width-fit-content]](https://drafts.csswg.org/css-sizing-4/#valdef-width-fit-content)

  -----------------------------------------------------------------------------------------------------

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

`fit-content`

46221--48

7979

943

No

331515--35

1172

464.44.4--48

462518--48

944

331414--35

1171

5.01.51.0--5.0

See also
--------

- Related sizing keywords: [`min-content`](min-content.md),
    [`max-content`](max-content.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/fit-content>
