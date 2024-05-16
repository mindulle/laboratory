element()
=========

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `element()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) defines an [`<image>`](_Resources/Markup%20And%20Styling/css/image.md) value generated
from an arbitrary HTML element. This image is live, meaning that if the
HTML element is changed, the CSS properties using the resulting value
are automatically updated.

A particularly useful scenario for using this would be to render an
image in an HTML
[`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas)
element, then use that as a background.

On Gecko browsers, you can use the non-standard
[`document.mozSetImageElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/mozSetImageElement)
method to change the element being used as the background for a given
CSS background element.

Syntax
------

[css]

```css
element(id)
```

where:

[*id*](#id)

:   The ID of an element to use as the background, specified using the
    HTML attribute \#*id* on the element.

Examples
--------

These examples work in builds of Firefox that support `-moz-element()`.

### A somewhat realistic example

This example uses a hidden
[`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)
as a background. The background element uses a gradient, but also
includes text that is rendered as part of the background.

[html]

```html
<div
  style="width:400px; height:400px; background:-moz-element(#myBackground1) no-repeat;">
  <p>This box uses the element with the #myBackground1 ID as its background!</p>
</div>

<div style="overflow:hidden; height:0;">
  <div
    id="myBackground1"
    style="width:1024px; height:1024px; background-image: linear-gradient(to right, red, orange, yellow, white);">
    <p style="transform-origin:0 0; rotate: 45deg; color:white;">
      This text is part of the background. Cool, huh?
    </p>
  </div>
</div>
```

The
[`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)
element with the ID \"myBackground1\" is used as the background for the
content including the paragraph \"This box uses the element with the
\#myBackground1 ID as its background!\".

### Page Preview

This [example based on Vincent De
Oliveira\'s](https://iamvdo.me/en/blog/css-element-function) creates a
preview of the `<div id="css-source">` inside `<div id="css-result">`.

#### HTML

[html]

```html
<div id="css-source">
  <h1>Page Preview</h1>
</div>
<div id="css-result"></div>
```

#### CSS

[css]

```css
#css-result {
  background: -moz-element(#css-source) no-repeat;
  width: 256px;
  height: 32px;
  background-size: 80%;
  border: dashed;
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------

  [CSS Images Module Level 4\
  [\#
  element-notation]](https://drafts.csswg.org/css-images-4/#element-notation)

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

`element()`

No

No

57

29--57`-moz-element()` is limited to
[`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image),
[`background`](https://developer.mozilla.org/docs/Web/CSS/background),
[`border-image`](https://developer.mozilla.org/docs/Web/CSS/border-image)
and
[`border-image-source`](https://developer.mozilla.org/docs/Web/CSS/border-image-source).

4--29`-moz-element()` is limited to
[`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image)
and
[`background`](https://developer.mozilla.org/docs/Web/CSS/background).

No

No

No

No

No

60

29--60`-moz-element()` is limited to
[`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image),
[`background`](https://developer.mozilla.org/docs/Web/CSS/background),
[`border-image`](https://developer.mozilla.org/docs/Web/CSS/border-image)
and
[`border-image-source`](https://developer.mozilla.org/docs/Web/CSS/border-image-source).

4--29`-moz-element()` is limited to
[`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image)
and
[`background`](https://developer.mozilla.org/docs/Web/CSS/background).

No

No

No

See also
--------

- [`image()`](_Resources/Markup%20And%20Styling/css/image/image.md)
- [`image-set()`](image-set.md)
- [`<image>`](_Resources/Markup%20And%20Styling/css/image.md)
- [`<gradient>`](gradient.md)
- [`cross-fade()`](cross-fade.md)
- [`document.mozSetImageElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/mozSetImageElement)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/element()>
