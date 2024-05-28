[dart:html](../../dart-html/dart-html-library){._links-link}

fontStyle property
==================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) fontStyle

::: {.features}
override
:::
:::

Gets the value of \"font-style\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get fontStyle => this._fontStyle;
```

::: {#setter .section .multi-line-signature}
void fontStyle=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"font-style\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set fontStyle(String? value) {
  _fontStyle = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/fontStyle.html>
:::
