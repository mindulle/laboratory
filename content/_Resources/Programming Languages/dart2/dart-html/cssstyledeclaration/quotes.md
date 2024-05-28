[dart:html](../../dart-html/dart-html-library){._links-link}

quotes property
===============

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) quotes

::: {.features}
override
:::
:::

Gets the value of \"quotes\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get quotes => this._quotes;
```

::: {#setter .section .multi-line-signature}
void quotes=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"quotes\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set quotes(String? value) {
  _quotes = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/quotes.html>
:::
