[dart:html](../../dart-html/dart-html-library){._links-link}

height property
===============

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) height

::: {.features}
override
:::
:::

Gets the value of \"height\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get height => this._height;
```

::: {#setter .section .multi-line-signature}
void height=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"height\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set height(String? value) {
  _height = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/height.html>
:::
