[dart:html](../../dart-html/dart-html-library){._links-link}

padding property
================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) padding

::: {.features}
override
:::
:::

Gets the value of \"padding\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get padding => this._padding;
```

::: {#setter .section .multi-line-signature}
void padding=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"padding\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set padding(String? value) {
  _padding = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/padding.html>
:::
