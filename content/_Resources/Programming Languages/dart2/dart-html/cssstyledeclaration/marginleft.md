[dart:html](../../dart-html/dart-html-library){._links-link}

marginLeft property
===================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) marginLeft

::: {.features}
override
:::
:::

Gets the value of \"margin-left\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get marginLeft => this._marginLeft;
```

::: {#setter .section .multi-line-signature}
void marginLeft=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"margin-left\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set marginLeft(String? value) {
  _marginLeft = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/marginLeft.html>
:::
