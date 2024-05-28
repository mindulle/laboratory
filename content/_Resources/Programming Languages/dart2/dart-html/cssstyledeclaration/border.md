[dart:html](../../dart-html/dart-html-library){._links-link}

border property
===============

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) border

::: {.features}
override
:::
:::

Gets the value of \"border\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get border => this._border;
```

::: {#setter .section .multi-line-signature}
void border=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"border\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set border(String? value) {
  _border = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/border.html>
:::
