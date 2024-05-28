[dart:html](../../dart-html/dart-html-library){._links-link}

toDataUrl method
================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) toDataUrl(

1.  \[[String](../../dart-core/string-class) type = \'image/png\',
2.  [num](../../dart-core/num-class)? quality\]

)
:::

Returns a data URI containing a representation of the image in the
format specified by type (defaults to \'image/png\').

Data Uri format is as follow
`data:[<MIME-type>][;charset=<encoding>][;base64],<data>`

Optional parameter `quality` in the range of 0.0 and 1.0 can be used
when requesting `type` \'image/jpeg\' or \'image/webp\'. If `quality` is
not passed the default value is used. Note: the default value varies by
browser.

If the height or width of this canvas element is 0, then \'data:\' is
returned, representing no data.

If the type requested is not \'image/png\', and the returned value is
\'data:image/png\', then the requested type is not supported.

Example usage:

``` {.language-dart data-language="dart"}
CanvasElement canvas = new CanvasElement();
var ctx = canvas.context2D
..fillStyle = "rgb(200,0,0)"
..fillRect(10, 10, 55, 50);
var dataUrl = canvas.toDataUrl("image/jpeg", 0.95);
// The Data Uri would look similar to
// 'data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA
// AAAFCAYAAACNbyblAAAAHElEQVQI12P4//8/w38GIAXDIBKE0DHxgljNBAAO
// 9TXL0Y4OHwAAAABJRU5ErkJggg=='
//Create a new image element from the data URI.
var img = new ImageElement();
img.src = dataUrl;
document.body.children.add(img);
```

See also:

-   [Data URI Scheme](http://en.wikipedia.org/wiki/Data_URI_scheme) from
    Wikipedia.

-   [HTMLCanvasElement](https://developer.mozilla.org/en-US/docs/DOM/HTMLCanvasElement)
    from MDN.

-   [toDataUrl](http://dev.w3.org/html5/spec/the-canvas-element.html#dom-canvas-todataurl)
    from W3C.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String toDataUrl([String type = 'image/png', num? quality]) =>
    _toDataUrl(type, quality);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasElement/toDataUrl.html>
:::
