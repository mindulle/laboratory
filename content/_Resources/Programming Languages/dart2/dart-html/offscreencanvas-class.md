[dart:html](../dart-html/dart-html-library){._links-link}

OffscreenCanvas class
=====================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   OffscreenCanvas

Annotations

:   -   \@Native(\"OffscreenCanvas\")

Constructors
------------

[OffscreenCanvas](offscreencanvas/offscreencanvas)([int](../dart-core/int-class)
width, [int](../dart-core/int-class) height)

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[height](offscreencanvas/height) ↔ [int](../dart-core/int-class)?

::: {.features}
read / write
:::

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[width](offscreencanvas/width) ↔ [int](../dart-core/int-class)?

::: {.features}
read / write
:::

Methods {#instance-methods}
-------

[addEventListener](eventtarget/addeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[convertToBlob](offscreencanvas/converttoblob)(\[[Map](../dart-core/map-class)?
options\]) → [Future](../dart-async/future-class)\<[Blob](blob-class)\>

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[getContext](offscreencanvas/getcontext)([String](../dart-core/string-class)
contextType, \[[Map](../dart-core/map-class)? attributes\]) →
[Object](../dart-core/object-class)?

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[removeEventListener](eventtarget/removeeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[transferToImageBitmap](offscreencanvas/transfertoimagebitmap)() →
[ImageBitmap](imagebitmap-class)

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
<https://api.dart.dev/stable/2.18.5/dart-html/OffscreenCanvas-class.html>
:::
