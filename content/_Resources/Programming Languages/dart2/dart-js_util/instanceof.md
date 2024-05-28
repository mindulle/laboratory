[dart:js\_util](../dart-js_util/dart-js_util-library){._links-link}

instanceof function
===================

::: {.section .multi-line-signature}
[bool](../dart-core/bool-class) instanceof(

1.  [Object](../dart-core/object-class)? o,
2.  [Object](../dart-core/object-class) type

)
:::

Check whether `o` is an instance of `type`.

The value in `type` is expected to be a JS-interop object that
represents a valid JavaScript constructor function.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external bool instanceof(Object? o, Object type);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-js_util/instanceof.html>
:::
