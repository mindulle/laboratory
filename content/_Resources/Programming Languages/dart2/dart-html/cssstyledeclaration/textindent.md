[dart:html](../../dart-html/dart-html-library){._links-link}

textIndent property
===================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) textIndent

::: {.features}
override
:::
:::

Gets the value of \"text-indent\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get textIndent => this._textIndent;
```

::: {#setter .section .multi-line-signature}
void textIndent=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"text-indent\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set textIndent(String? value) {
  _textIndent = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/textIndent.html>
:::
