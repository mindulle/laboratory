[dart:html](../../dart-html/dart-html-library){._links-link}

lineHeight property
===================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) lineHeight

::: {.features}
override
:::
:::

Gets the value of \"line-height\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get lineHeight => this._lineHeight;
```

::: {#setter .section .multi-line-signature}
void lineHeight=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"line-height\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set lineHeight(String? value) {
  _lineHeight = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/lineHeight.html>
:::
