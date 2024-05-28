[dart:html](../../dart-html/dart-html-library){._links-link}

backgroundImage property
========================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) backgroundImage

::: {.features}
override
:::
:::

Gets the value of \"background-image\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get backgroundImage => this._backgroundImage;
```

::: {#setter .section .multi-line-signature}
void backgroundImage=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"background-image\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set backgroundImage(String? value) {
  _backgroundImage = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/backgroundImage.html>
:::
