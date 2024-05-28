[dart:html](../../dart-html/dart-html-library){._links-link}

content property
================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) content

::: {.features}
override
:::
:::

Gets the value of \"content\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get content => this._content;
```

::: {#setter .section .multi-line-signature}
void content=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"content\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set content(String? value) {
  _content = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/content.html>
:::
