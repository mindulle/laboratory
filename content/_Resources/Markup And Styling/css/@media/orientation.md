orientation
===========

The `orientation`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](@media.md#media_features) can be used to test the orientation
of the
[viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport)
(or the page box, for [paged media](css_paged_media.md)).

**Note:** This feature does not correspond to *device* orientation.
Opening the soft keyboard on many devices in portrait orientation will
cause the viewport to become wider than it is tall, thereby causing the
browser to use landscape styles instead of portrait.

Syntax
------

The `orientation` feature is specified as a keyword value chosen from
the list below.

### Keyword values

[`portrait`](#portrait)

:   The viewport is in a portrait orientation, i.e., the height is
    greater than or equal to the width.

[`landscape`](#landscape)

:   The viewport is in a landscape orientation, i.e., the width is
    greater than the height.

Examples
--------

### Portrait orientation

In this example we have three boxes in the HTML, and use the
`orientation` media feature to switch between a row layout (in
landscape) and a column layout (in portrait).

The example output is embedded in an
[`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)
whose height is greater than its width, so the boxes get a column
layout.

#### HTML

[html]

```html
<div>Box 1</div>
<div>Box 2</div>
<div>Box 3</div>
```

#### CSS

[css]

```css
body {
  display: flex;
}

div {
  background: yellow;
  width: 200px;
  height: 200px;
  margin: 0.5rem;
  padding: 0.5rem;
}

@media (orientation: landscape) {
  body {
    flex-direction: row;
  }
}

@media (orientation: portrait) {
  body {
    flex-direction: column;
  }
}
```

#### Result

### Landscape orientation

This example has exactly the same code as the previous example: it has
three boxes in the HTML, and uses the `orientation` media feature to
switch between a row layout (in landscape) and a column layout (in
portrait).

However, in this example, the example output is embedded in an
[`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)
whose height is less than its width, so the boxes get a row layout.

#### HTML

[html]

```html
<div>Box 1</div>
<div>Box 2</div>
<div>Box 3</div>
```

#### CSS

[css]

```css
body {
  display: flex;
}

div {
  background: yellow;
  width: 200px;
  height: 200px;
  margin: 0.5rem;
  padding: 0.5rem;
}

@media (orientation: landscape) {
  body {
    flex-direction: row;
  }
}

@media (orientation: portrait) {
  body {
    flex-direction: column;
  }
}
```

Specifications
--------------

  ---------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------

  [Media Queries Level 4\
  [\#
  orientation]](https://drafts.csswg.org/mediaqueries/#orientation)

  ---------------------------------------------------------------------------

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

`orientation`

3

12

2

9

10.6

5

≤37

18

4

11

4.2

1.0

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/orientation>
