[dart:js\_util](../dart-js_util/dart-js_util-library){._links-link}

isJavaScriptSimpleObject function
=================================

::: {.section .multi-line-signature}
[bool](../dart-core/bool-class) isJavaScriptSimpleObject(

1.  dynamic value

)
:::

Returns `true` if a given object is a simple JavaScript object.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool isJavaScriptSimpleObject(value) {
  final Object? proto = objectGetPrototypeOf(value);
  return proto == null || proto == objectPrototype;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-js_util/isJavaScriptSimpleObject.html>
:::
