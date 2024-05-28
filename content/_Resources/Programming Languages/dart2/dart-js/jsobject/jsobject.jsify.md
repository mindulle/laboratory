[dart:js](../../dart-js/dart-js-library){._links-link}

JsObject.jsify constructor
==========================

::: {.section .multi-line-signature}
JsObject.jsify(

1.  [Object](../../dart-core/object-class) object

)
:::

Recursively converts a JSON-like collection of Dart objects to a
collection of JavaScript objects and returns a
[JsObject](../jsobject-class) proxy to it.

`object` must be a [Map](../../dart-core/map-class) or
[Iterable](../../dart-core/iterable-class), the contents of which are
also converted. Maps and Iterables are copied to a new JavaScript
object. Primitives and other transferable values are directly converted
to their JavaScript type, and all other objects are proxied.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory JsObject.jsify(Object object);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-js/JsObject/JsObject.jsify.html>
:::
