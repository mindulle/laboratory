[dart:html](../../dart-html/dart-html-library){._links-link}

zIndex property
===============

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) zIndex

::: {.features}
override
:::
:::

Gets the value of \"z-index\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get zIndex => this._zIndex;
```

::: {#setter .section .multi-line-signature}
void zIndex=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"z-index\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set zIndex(String? value) {
  _zIndex = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/zIndex.html>
:::
