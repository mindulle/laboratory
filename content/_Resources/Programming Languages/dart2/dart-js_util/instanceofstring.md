[dart:js\_util](../dart-js_util/dart-js_util-library){._links-link}

instanceOfString function
=========================

::: {.section .multi-line-signature}
[bool](../dart-core/bool-class) instanceOfString(

1.  [Object](../dart-core/object-class)? element,
2.  [String](../dart-core/string-class) objectType

)
:::

Like [instanceof](instanceof) only takes a
[String](../dart-core/string-class) for the object name instead of a
constructor object.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool instanceOfString(Object? element, String objectType) {
  Object? constructor = _getConstructor(objectType);
  return constructor != null && instanceof(element, constructor);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-js_util/instanceOfString.html>
:::
