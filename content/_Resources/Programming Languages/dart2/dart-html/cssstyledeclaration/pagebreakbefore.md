[dart:html](../../dart-html/dart-html-library){._links-link}

pageBreakBefore property
========================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) pageBreakBefore

::: {.features}
override
:::
:::

Gets the value of \"page-break-before\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get pageBreakBefore => this._pageBreakBefore;
```

::: {#setter .section .multi-line-signature}
void pageBreakBefore=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Sets the value of \"page-break-before\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set pageBreakBefore(String? value) {
  _pageBreakBefore = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/pageBreakBefore.html>
:::
