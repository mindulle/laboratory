[dart:html](../../dart-html/dart-html-library){._links-link}

fontFamily property
===================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) fontFamily

::: {.features}
override
:::
:::

Gets the value of \"font-family\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get fontFamily => this._fontFamily;
```

::: {#setter .section .multi-line-signature}
void fontFamily=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"font-family\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set fontFamily(String? value) {
  _fontFamily = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/fontFamily.html>
:::
