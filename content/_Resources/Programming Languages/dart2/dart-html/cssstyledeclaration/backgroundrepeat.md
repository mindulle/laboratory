[dart:html](../../dart-html/dart-html-library){._links-link}

backgroundRepeat property
=========================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) backgroundRepeat

::: {.features}
override
:::
:::

Gets the value of \"background-repeat\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get backgroundRepeat => this._backgroundRepeat;
```

::: {#setter .section .multi-line-signature}
void backgroundRepeat=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"background-repeat\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set backgroundRepeat(String? value) {
  _backgroundRepeat = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/backgroundRepeat.html>
:::
