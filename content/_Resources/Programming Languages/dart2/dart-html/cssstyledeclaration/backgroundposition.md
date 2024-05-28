[dart:html](../../dart-html/dart-html-library){._links-link}

backgroundPosition property
===========================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) backgroundPosition

::: {.features}
override
:::
:::

Gets the value of \"background-position\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get backgroundPosition => this._backgroundPosition;
```

::: {#setter .section .multi-line-signature}
void backgroundPosition=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"background-position\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set backgroundPosition(String? value) {
  _backgroundPosition = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/backgroundPosition.html>
:::
