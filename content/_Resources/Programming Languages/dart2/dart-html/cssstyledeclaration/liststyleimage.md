[dart:html](../../dart-html/dart-html-library){._links-link}

listStyleImage property
=======================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) listStyleImage

::: {.features}
override
:::
:::

Gets the value of \"list-style-image\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get listStyleImage => this._listStyleImage;
```

::: {#setter .section .multi-line-signature}
void listStyleImage=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"list-style-image\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set listStyleImage(String? value) {
  _listStyleImage = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/listStyleImage.html>
:::
