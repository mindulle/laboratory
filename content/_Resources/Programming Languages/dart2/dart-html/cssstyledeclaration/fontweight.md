[dart:html](../../dart-html/dart-html-library){._links-link}

fontWeight property
===================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) fontWeight

::: {.features}
override
:::
:::

Gets the value of \"font-weight\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get fontWeight => this._fontWeight;
```

::: {#setter .section .multi-line-signature}
void fontWeight=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"font-weight\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set fontWeight(String? value) {
  _fontWeight = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/fontWeight.html>
:::
