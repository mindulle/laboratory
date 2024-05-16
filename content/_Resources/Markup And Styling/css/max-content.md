max-content
===========

The `max-content` sizing keyword represents the intrinsic maximum width
or height of the content. For text content this means that the content
will not wrap at all even if it causes overflows.

Syntax
------

[css]

```css
/* Used as a length */
width: max-content;
inline-size: max-content;
height: max-content;
block-size: max-content;

/* used in grid tracks */
grid-template-columns: 200px 1fr max-content;
```

Examples
--------

### Using max-content for box sizing

#### HTML

[html]

```html
<div id="container">
  <div class="item">Item</div>
  <div class="item">
    Item with more text in it which will overflow the fixed width box.
  </div>
</div>
```

#### CSS

[css]

```css
#container {
  background-color: #8cffa0;
  padding: 10px;
  width: 200px;
}

.item {
  width: max-content;
  background-color: #8ca0ff;
  padding: 5px;
  margin-bottom: 1em;
}
```

#### Result

### Sizing grid columns with max-content

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
  grid-template-columns: max-content max-content 1fr;
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
  valdef-width-max-content]](https://drafts.csswg.org/css-sizing-3/#valdef-width-max-content)

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

`max-content`

4622

7979

663

No

44

112

46

46

664

43

111

5.0

See also
--------

- Related sizing keywords: [`min-content`](min-content.md),
    [`fit-content`](fit-content.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/max-content>
