[dart:html](../../dart-html/dart-html-library){._links-link}

emptyCells property
===================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) emptyCells

::: {.features}
override
:::
:::

Gets the value of \"empty-cells\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get emptyCells => this._emptyCells;
```

::: {#setter .section .multi-line-signature}
void emptyCells=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"empty-cells\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set emptyCells(String? value) {
  _emptyCells = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/emptyCells.html>
:::
