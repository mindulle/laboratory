[dart:html](../../dart-html/dart-html-library){._links-link}

listStyleType property
======================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) listStyleType

::: {.features}
override
:::
:::

Gets the value of \"list-style-type\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get listStyleType => this._listStyleType;
```

::: {#setter .section .multi-line-signature}
void listStyleType=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"list-style-type\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set listStyleType(String? value) {
  _listStyleType = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/listStyleType.html>
:::
