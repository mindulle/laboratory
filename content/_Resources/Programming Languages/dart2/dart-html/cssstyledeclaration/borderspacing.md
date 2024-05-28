[dart:html](../../dart-html/dart-html-library){._links-link}

borderSpacing property
======================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) borderSpacing

::: {.features}
override
:::
:::

Gets the value of \"border-spacing\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get borderSpacing => this._borderSpacing;
```

::: {#setter .section .multi-line-signature}
void borderSpacing=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"border-spacing\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set borderSpacing(String? value) {
  _borderSpacing = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/borderSpacing.html>
:::
