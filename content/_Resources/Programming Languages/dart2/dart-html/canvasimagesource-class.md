[dart:html](../dart-html/dart-html-library){._links-link}

CanvasImageSource class
=======================

An object that can be drawn to a 2D canvas rendering context.

The image drawn to the canvas depends on the type of this object:

-   If this object is an [ImageElement](imageelement-class), then this
    element\'s image is drawn to the canvas. If this element is an
    animated image, then this element\'s poster frame is drawn. If this
    element has no poster frame, then the first frame of animation is
    drawn.

-   If this object is a [VideoElement](videoelement-class), then the
    frame at this element\'s current playback position is drawn to the
    canvas.

-   If this object is a [CanvasElement](canvaselement-class), then this
    element\'s bitmap is drawn to the canvas.

**Note:** Currently all versions of Internet Explorer do not support
drawing a video element to a canvas. You may also encounter problems
drawing a video to a canvas in Firefox if the source of the video is a
data URL.

See also
--------

-   [CanvasRenderingContext2D.drawImage](canvasrenderingcontext2d/drawimage)
-   [CanvasRenderingContext2D.drawImageToRect](canvasrenderingcontext2d/drawimagetorect)
-   [CanvasRenderingContext2D.drawImageScaled](canvasrenderingcontext2d/drawimagescaled)
-   [CanvasRenderingContext2D.drawImageScaledFromSource](canvasrenderingcontext2d/drawimagescaledfromsource)

Other resources
---------------

-   [Image sources for 2D rendering
    contexts](https://html.spec.whatwg.org/multipage/scripting.html#image-sources-for-2d-rendering-contexts)
    from WHATWG.
-   [Drawing
    images](https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-drawimage)
    from WHATWG.

Implementers

:   -   [CanvasElement](canvaselement-class)
    -   [ImageElement](imageelement-class)
    -   [VideoElement](videoelement-class)

Constructors
------------

[CanvasImageSource](canvasimagesource/canvasimagesource)()

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
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasImageSource-class.html>
:::
