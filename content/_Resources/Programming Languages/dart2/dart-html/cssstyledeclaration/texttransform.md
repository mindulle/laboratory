[dart:html](../../dart-html/dart-html-library){._links-link}

textTransform property
======================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) textTransform

::: {.features}
override
:::
:::

Gets the value of \"text-transform\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get textTransform => this._textTransform;
```

::: {#setter .section .multi-line-signature}
void textTransform=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"text-transform\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set textTransform(String? value) {
  _textTransform = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/textTransform.html>
:::
