[dart:html](../dart-html/dart-html-library){._links-link}

CanvasPattern class
===================

An opaque object representing a pattern of image, canvas, or video.

Created by calling
[CanvasRenderingContext2D.createPattern](canvasrenderingcontext2d/createpattern)
on a [CanvasRenderingContext2D](canvasrenderingcontext2d-class) object.

Example usage:

``` {.language-dart data-language="dart"}
var canvas = new CanvasElement(width: 600, height: 600);
var ctx = canvas.context2D;
var img = new ImageElement();
// Image src needs to be loaded before pattern is applied.
img.onLoad.listen((event) {
  // When the image is loaded, create a pattern
  // from the ImageElement.
  CanvasPattern pattern = ctx.createPattern(img, 'repeat');
  ctx.rect(0, 0, canvas.width, canvas.height);
  ctx.fillStyle = pattern;
  ctx.fill();
});
img.src = "images/foo.jpg";
document.body.children.add(canvas);
```

See also:

-   [CanvasPattern](https://developer.mozilla.org/en-US/docs/DOM/CanvasPattern)
    from MDN.
-   [CanvasPattern](https://html.spec.whatwg.org/multipage/scripting.html#canvaspattern)
    from WHATWG.
-   [CanvasPattern](http://www.w3.org/TR/2010/WD-2dcontext-20100304/#canvaspattern)
    from W3C.

Annotations

:   -   \@Native(\"CanvasPattern\")

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[setTransform](canvaspattern/settransform)([Matrix](../dart-svg/matrix-class)
transform) → void

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasPattern-class.html>
:::
