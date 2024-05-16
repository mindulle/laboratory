\<canvas\>: The Graphics Canvas element
=======================================

Use the `<canvas>` with either the [canvas scripting
API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API) or the
[WebGL API](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API)
to draw graphics and animations.

  --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), [embedded content](../content_categories#embedded_content), palpable content.
  Permitted content                             Transparent but with no [interactive content](../content_categories#interactive_content) descendants except for [`<a>`](a) elements, [`<button>`](button) elements, [`<input>`](input) elements whose [`type`](input#type) attribute is `checkbox`, `radio`, or `button`.
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLCanvasElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement)
  --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Attributes
----------

This element\'s attributes include the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`height`](#height)

:   The height of the coordinate space in CSS pixels. Defaults to 150.

[`moz-opaque`](#moz-opaque) [Non-standard]

:   Lets the canvas know whether translucency will be a factor. If the
    canvas knows there\'s no translucency, painting performance can be
    optimized. This is only supported by Mozilla-based browsers; use the
    standardized
    [`canvas.getContext('2d', { alpha: false })`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/getContext)
    instead.

[`width`](#width)

:   The width of the coordinate space in CSS pixels. Defaults to 300.

Usage notes
-----------

### Alternative content

You should provide alternate content inside the `<canvas>` block. That
content will be rendered both on older browsers that don\'t support
canvas and in browsers with JavaScript disabled.

### Closing `</canvas>` tag

Unlike the [`<img>`](img) element, the [`<canvas>`](canvas) element
**requires** the closing tag (`</canvas>`).

### Sizing the canvas using CSS versus HTML

The displayed size of the canvas can be changed using CSS, but if you do
this the image is scaled during rendering to fit the styled size, which
can make the final graphics rendering end up being distorted.

It is better to specify your canvas dimensions by setting the `width`
and `height` attributes directly on the `<canvas>` elements, either
directly in the HTML or by using JavaScript.

### Maximum canvas size

The maximum size of a `<canvas>` element is very large, but the exact
size depends on the browser. The following is some data we\'ve collected
from various tests and other sources (e.g. [Stack
Overflow](https://stackoverflow.com/questions/6081483/maximum-size-of-a-canvas-element)):

  Browser   Maximum height   Maximum width   Maximum area
  --------- ---------------- --------------- --------------------------------------------
  Chrome    32,767 pixels    32,767 pixels   268,435,456 pixels (i.e., 16,384 x 16,384)
  Firefox   32,767 pixels    32,767 pixels   472,907,776 pixels (i.e., 22,528 x 20,992)
  Safari    32,767 pixels    32,767 pixels   268,435,456 pixels (i.e., 16,384 x 16,384)
  IE        8,192 pixels     8,192 pixels    ?

**Note:** Exceeding the maximum dimensions or area renders the canvas
unusable --- drawing commands will not work.

### Using an offscreen canvas

A canvas can be rendered using the
[`OffscreenCanvas`](https://developer.mozilla.org/en-US/docs/Web/API/OffscreenCanvas)
API where the document and canvas are decoupled. The benefit is that a
[worker
thread](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers)
can handle canvas rendering and the main thread of your web application
is not blocked by canvas operations. By parallelizing work, other UI
elements of your web application will remain responsive even if you are
running complex graphics on an offscreen canvas. For more information,
see the
[`OffscreenCanvas`](https://developer.mozilla.org/en-US/docs/Web/API/OffscreenCanvas)
API documentation.

Examples
--------

### HTML

This code snippet adds a canvas element to your HTML document. A
fallback text is provided if a browser is unable to read or render the
canvas.

[html]

```html
<canvas width="120" height="120">
  An alternative text describing what your canvas displays.
</canvas>
```

### JavaScript

Then in the JavaScript code, call
[`HTMLCanvasElement.getContext()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/getContext)
to get a drawing context and start drawing onto the canvas:

[js]

```js
const canvas = document.querySelector("canvas");
const ctx = canvas.getContext("2d");
ctx.fillStyle = "green";
// Add a rectangle at (10, 10) with size 100x100 pixels
ctx.fillRect(10, 10, 100, 100);
```

### Result

Accessibility concerns
----------------------

### Alternative content

The `<canvas>` element on its own is just a bitmap and does not provide
information about any drawn objects. Canvas content is not exposed to
accessibility tools as semantic HTML is. In general, you should avoid
using canvas in an accessible website or app. The following guides can
help to make it more accessible.

- [Canvas accessibility use
    cases](https://www.w3.org/WAI/PF/HTML/wiki/Canvas_Accessibility_Use_Cases)
- [Canvas element accessibility
    issues](https://www.w3.org/html/wg/wiki/AddedElementCanvas)
- [HTML Canvas Accessibility in Firefox 13 -- by Steve
    Faulkner](https://www.tpgi.com/html5-canvas-accessibility-in-firefox-13/)
- [Best practices for interactive canvas
    elements](https://html.spec.whatwg.org/multipage/scripting.html#best-practices)

Specifications
--------------

  -----------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-canvas-element]](https://html.spec.whatwg.org/multipage/canvas.html#the-canvas-element)

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

`canvas`

1

12

1.5\[\"Before Firefox 5, the canvas width and height were signed
integers instead of unsigned integers.\", \"Before Firefox 6, a
\<canvas\> element with a zero width or height would be rendered as if
it had default dimensions.\", \"Before Firefox 12, if JavaScript is
disabled, the \<canvas\> element was being rendered instead of showing
the fallback content as per the specification. Since then, the fallback
content is rendered instead.\"\]

9

9

2Although early versions of Apple\'s Safari browser don\'t require the
closing tag, the specification indicates that it is required, so you
should be sure to include it for broadest compatibility. Before version
2, Safari will render the content of the fallback in addition to the
canvas itself unless you use CSS tricks to mask it.

37

18

4\[\"Before Firefox 5, the canvas width and height were signed integers
instead of unsigned integers.\", \"Before Firefox 6, a \<canvas\>
element with a zero width or height would be rendered as if it had
default dimensions.\", \"Before Firefox 12, if JavaScript is disabled,
the \<canvas\> element was being rendered instead of showing the
fallback content as per the specification. Since then, the fallback
content is rendered instead.\"\]

10.1

1

1.0

`height`

1

12

1.5\[\"Before Firefox 5, the canvas width and height were signed
integers instead of unsigned integers.\", \"Before Firefox 6, a
\<canvas\> element with a zero width or height would be rendered as if
it had default dimensions.\", \"Before Firefox 12, if JavaScript is
disabled, the \<canvas\> element was being rendered instead of showing
the fallback content as per the specification. Since then, the fallback
content is rendered instead.\"\]

9

9

2Although early versions of Apple\'s Safari browser don\'t require the
closing tag, the specification indicates that it is required, so you
should be sure to include it for broadest compatibility. Before version
2, Safari will render the content of the fallback in addition to the
canvas itself unless you use CSS tricks to mask it.

37

18

4\[\"Before Firefox 5, the canvas width and height were signed integers
instead of unsigned integers.\", \"Before Firefox 6, a \<canvas\>
element with a zero width or height would be rendered as if it had
default dimensions.\", \"Before Firefox 12, if JavaScript is disabled,
the \<canvas\> element was being rendered instead of showing the
fallback content as per the specification. Since then, the fallback
content is rendered instead.\"\]

10.1

1

1.0

`moz-opaque`

No

No

3.5

No

No

No

No

No

4

No

No

No

`width`

1

12

1.5\[\"Before Firefox 5, the canvas width and height were signed
integers instead of unsigned integers.\", \"Before Firefox 6, a
\<canvas\> element with a zero width or height would be rendered as if
it had default dimensions.\", \"Before Firefox 12, if JavaScript is
disabled, the \<canvas\> element was being rendered instead of showing
the fallback content as per the specification. Since then, the fallback
content is rendered instead.\"\]

9

9

2Although early versions of Apple\'s Safari browser don\'t require the
closing tag, the specification indicates that it is required, so you
should be sure to include it for broadest compatibility. Before version
2, Safari will render the content of the fallback in addition to the
canvas itself unless you use CSS tricks to mask it.

37

18

4\[\"Before Firefox 5, the canvas width and height were signed integers
instead of unsigned integers.\", \"Before Firefox 6, a \<canvas\>
element with a zero width or height would be rendered as if it had
default dimensions.\", \"Before Firefox 12, if JavaScript is disabled,
the \<canvas\> element was being rendered instead of showing the
fallback content as per the specification. Since then, the fallback
content is rendered instead.\"\]

10.1

1

1.0

See also
--------

- [Canvas
    API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
- [Canvas
    tutorial](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial)
- [Canvas-related
    demos](https://developer.mozilla.org/en-US/docs/Web/Demos#canvas)
- [OffscreenCanvas](https://developer.mozilla.org/en-US/docs/Web/API/OffscreenCanvas)
- [Canvas cheat
    sheet](https://simon.html5.org/dump/html5-canvas-cheat-sheet.html) (2009)
- [Canvas cheat
    sheet](https://websitesetup.org/wp-content/uploads/2015/11/Infopgraphic-CanvasCheatSheet-Final2.pdf)
    (pdf) (2015)
- [Canvas cheat
    sheet](https://www.coding-dude.com/wp/wp-content/uploads/2020/09/HTML5-canvas-cheat-sheet.pdf)
    (pdf) (2020)
- [Canvas introduction by
    Apple](https://developer.apple.com/library/archive/documentation/AudioVideo/Conceptual/HTML-canvas-guide/Introduction/Introduction.html) (2013)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas>>
