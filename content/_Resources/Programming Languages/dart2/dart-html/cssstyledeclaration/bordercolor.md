[dart:html](../../dart-html/dart-html-library){._links-link}

borderColor property
====================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) borderColor

::: {.features}
override
:::
:::

Gets the value of \"border-color\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get borderColor => this._borderColor;
```

::: {#setter .section .multi-line-signature}
void borderColor=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"border-color\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set borderColor(String? value) {
  _borderColor = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/borderColor.html>
:::
