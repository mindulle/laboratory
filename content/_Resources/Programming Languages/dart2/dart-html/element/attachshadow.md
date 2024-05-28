[dart:html](../../dart-html/dart-html-library){._links-link}

attachShadow method
===================

::: {.section .multi-line-signature}
[ShadowRoot](../shadowroot-class) attachShadow(

1.  [Map](../../dart-core/map-class) shadowRootInitDict

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ShadowRoot attachShadow(Map shadowRootInitDict) {
  var shadowRootInitDict_1 =
      convertDartToNative_Dictionary(shadowRootInitDict);
  return _attachShadow_1(shadowRootInitDict_1);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/attachShadow.html>
:::
