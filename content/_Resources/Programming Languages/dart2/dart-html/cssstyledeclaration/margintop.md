[dart:html](../../dart-html/dart-html-library){._links-link}

marginTop property
==================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) marginTop

::: {.features}
override
:::
:::

Gets the value of \"margin-top\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get marginTop => this._marginTop;
```

::: {#setter .section .multi-line-signature}
void marginTop=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"margin-top\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set marginTop(String? value) {
  _marginTop = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/marginTop.html>
:::
