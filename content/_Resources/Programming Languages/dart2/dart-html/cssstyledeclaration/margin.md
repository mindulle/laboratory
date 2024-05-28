[dart:html](../../dart-html/dart-html-library){._links-link}

margin property
===============

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) margin

::: {.features}
override
:::
:::

Gets the value of \"margin\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get margin => this._margin;
```

::: {#setter .section .multi-line-signature}
void margin=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"margin\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set margin(String? value) {
  _margin = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/margin.html>
:::
