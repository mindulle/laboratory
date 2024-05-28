[dart:html](../../dart-html/dart-html-library){._links-link}

letterSpacing property
======================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) letterSpacing

::: {.features}
override
:::
:::

Gets the value of \"letter-spacing\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get letterSpacing => this._letterSpacing;
```

::: {#setter .section .multi-line-signature}
void letterSpacing=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"letter-spacing\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set letterSpacing(String? value) {
  _letterSpacing = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/letterSpacing.html>
:::
