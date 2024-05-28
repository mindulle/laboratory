[dart:js\_util](../dart-js_util/dart-js_util-library){._links-link}

jsify function
==============

::: {.section .multi-line-signature}
dynamic jsify(

1.  [Object](../dart-core/object-class) object

)
:::

Recursively converts a JSON-like collection to JavaScript compatible
representation.

WARNING: performance of this method is much worse than other util
methods in this library. Only use this method as a last resort. Prefer
instead to use `@anonymous` `@JS()` annotated classes to create map-like
objects for JS interop.

The argument must be a [Map](../dart-core/map-class) or
[Iterable](../dart-core/iterable-class), the contents of which are also
deeply converted. Maps are converted into JavaScript objects. Iterables
are converted into arrays. Strings, numbers, bools, and `@JS()`
annotated objects are passed through unmodified. Dart objects are also
passed through unmodified, but their members aren\'t usable from
JavaScript.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external dynamic jsify(Object object);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-js_util/jsify.html>
:::
