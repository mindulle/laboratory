[dart:html](../dart-html/dart-html-library){._links-link}

ImageCapture class
==================

Annotations

:   -   \@Native(\"ImageCapture\")

Constructors
------------

[ImageCapture](imagecapture/imagecapture)([MediaStreamTrack](mediastreamtrack-class)
track)

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

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[track](imagecapture/track) →
[MediaStreamTrack](mediastreamtrack-class)?

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[getPhotoCapabilities](imagecapture/getphotocapabilities)() →
[Future](../dart-async/future-class)\<[PhotoCapabilities](photocapabilities-class)\>

[getPhotoSettings](imagecapture/getphotosettings)() →
[Future](../dart-async/future-class)\<[Map](../dart-core/map-class)\<[String](../dart-core/string-class),
dynamic\>?\>

[grabFrame](imagecapture/grabframe)() →
[Future](../dart-async/future-class)\<[ImageBitmap](imagebitmap-class)\>

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[setOptions](imagecapture/setoptions)([Map](../dart-core/map-class)
photoSettings) → [Future](../dart-async/future-class)

[takePhoto](imagecapture/takephoto)(\[[Map](../dart-core/map-class)?
photoSettings\]) →
[Future](../dart-async/future-class)\<[Blob](blob-class)\>

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
<https://api.dart.dev/stable/2.18.5/dart-html/ImageCapture-class.html>
:::
