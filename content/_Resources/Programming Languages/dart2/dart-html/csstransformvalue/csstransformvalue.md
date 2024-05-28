[dart:html](../../dart-html/dart-html-library){._links-link}

CssTransformValue constructor
=============================

::: {.section .multi-line-signature}
CssTransformValue(

1.  \[[List](../../dart-core/list-class)\<[CssTransformComponent](../csstransformcomponent-class)\>?
    transformComponents\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory CssTransformValue(
    [List<CssTransformComponent>? transformComponents]) {
  if (transformComponents == null) {
    return CssTransformValue._create_1();
  }
  if ((transformComponents is List<CssTransformComponent>)) {
    return CssTransformValue._create_2(transformComponents);
  }
  throw new ArgumentError("Incorrect number or type of arguments");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssTransformValue/CssTransformValue.html>
:::
