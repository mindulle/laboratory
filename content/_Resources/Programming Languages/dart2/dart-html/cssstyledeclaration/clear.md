[dart:html](../../dart-html/dart-html-library){._links-link}

clear property
==============

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) clear

::: {.features}
override
:::
:::

Gets the value of \"clear\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get clear => this._clear;
```

::: {#setter .section .multi-line-signature}
void clear=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"clear\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set clear(String? value) {
  _clear = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/clear.html>
:::
