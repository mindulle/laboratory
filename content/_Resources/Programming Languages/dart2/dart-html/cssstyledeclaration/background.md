[dart:html](../../dart-html/dart-html-library){._links-link}

background property
===================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) background

::: {.features}
override
:::
:::

Gets the value of \"background\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get background => this._background;
```

::: {#setter .section .multi-line-signature}
void background=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"background\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set background(String? value) {
  _background = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/background.html>
:::
