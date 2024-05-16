min-content
===========

The `min-content` sizing keyword represents the intrinsic minimum width
of the content. For text content this means that the content will take
all soft-wrapping opportunities, becoming as small as the longest word.

Syntax
------

[css]

```css
/* Used as a length */
width: min-content;
inline-size: min-content;
height: min-content;
block-size: min-content;

/* used in grid tracks */
grid-template-columns: 200px 1fr min-content;
```

Examples
--------

### Using min-content for box sizing

#### HTML

[html]

```html
<div class="item">Item</div>
<div class="item">Item with more text in it.</div>
```

#### CSS

[css]

```css
.item {
  width: min-content;
  background-color: #8ca0ff;
  padding: 5px;
  margin-bottom: 1em;
}
```

#### Result

### Sizing grid columns with min-content

#### HTML

[html]

```html
<div id="container">
  <div>Item</div>
  <div>Item with more text in it.</div>
  <div>Flexible item</div>
</div>
```

#### CSS

[css]

```css
#container {
  display: grid;
  grid-template-columns: min-content min-content 1fr;
  grid-gap: 5px;
  box-sizing: border-box;
  height: 200px;
  width: 100%;
  background-color: #8cffa0;
  padding: 10px;
}

#container > div {
  background-color: #8ca0ff;
  padding: 5px;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------

  [CSS Box Sizing Module Level 3\
  [\#
  valdef-width-min-content]](https://drafts.csswg.org/css-sizing-3/#valdef-width-min-content)

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

`min-content`

461--48

79

663

No

3315--35

112

464.4--48

4618--48

664

3314--35

111

5.01.0--5.0

See also
--------

- Related sizing keywords: [`max-content`](max-content.md),
    [`fit-content`](fit-content.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/min-content>
