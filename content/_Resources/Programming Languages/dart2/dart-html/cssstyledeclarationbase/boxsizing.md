[dart:html](../../dart-html/dart-html-library){._links-link}

boxSizing property
==================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) boxSizing
:::

Gets the value of \"box-sizing\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get boxSizing => getPropertyValue('box-sizing');
```

::: {#setter .section .multi-line-signature}
void boxSizing=([String](../../dart-core/string-class) value)
:::

Sets the value of \"box-sizing\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set boxSizing(String value) {
  setProperty('box-sizing', value, '');
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclarationBase/boxSizing.html>
:::
