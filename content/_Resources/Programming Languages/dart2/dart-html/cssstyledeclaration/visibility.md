[dart:html](../../dart-html/dart-html-library){._links-link}

visibility property
===================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) visibility

::: {.features}
override
:::
:::

Gets the value of \"visibility\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get visibility => this._visibility;
```

::: {#setter .section .multi-line-signature}
void visibility=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"visibility\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set visibility(String? value) {
  _visibility = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/visibility.html>
:::
