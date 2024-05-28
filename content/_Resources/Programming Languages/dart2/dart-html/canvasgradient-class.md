[dart:html](../dart-html/dart-html-library){._links-link}

CanvasGradient class
====================

An opaque canvas object representing a gradient.

Created by calling the methods
[CanvasRenderingContext2D.createLinearGradient](canvasrenderingcontext2d/createlineargradient)
or
[CanvasRenderingContext2D.createRadialGradient](canvasrenderingcontext2d/createradialgradient)
on a [CanvasRenderingContext2D](canvasrenderingcontext2d-class) object.

Example usage:

``` {.language-dart data-language="dart"}
var canvas = new CanvasElement(width: 600, height: 600);
var ctx = canvas.context2D;
ctx.clearRect(0, 0, 600, 600);
ctx.save();
// Create radial gradient.
CanvasGradient gradient = ctx.createRadialGradient(0, 0, 0, 0, 0, 600);
gradient.addColorStop(0, '#000');
gradient.addColorStop(1, 'rgb(255, 255, 255)');
// Assign gradients to fill.
ctx.fillStyle = gradient;
// Draw a rectangle with a gradient fill.
ctx.fillRect(0, 0, 600, 600);
ctx.save();
document.body.children.add(canvas);
```

See also:

-   [CanvasGradient](https://developer.mozilla.org/en-US/docs/DOM/CanvasGradient)
    from MDN.
-   [CanvasGradient](https://html.spec.whatwg.org/multipage/scripting.html#canvasgradient)
    from WHATWG.
-   [CanvasGradient](http://www.w3.org/TR/2010/WD-2dcontext-20100304/#canvasgradient)
    from W3C.

Annotations

:   -   \@Native(\"CanvasGradient\")

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

[addColorStop](canvasgradient/addcolorstop)([num](../dart-core/num-class)
offset, [String](../dart-core/string-class) color) → void

Adds a color stop to this gradient at the offset.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

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
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasGradient-class.html>
:::
