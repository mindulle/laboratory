[dart:html](../../dart-html/dart-html-library){._links-link}

backgroundAttachment property
=============================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) backgroundAttachment

::: {.features}
override
:::
:::

Gets the value of \"background-attachment\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get backgroundAttachment => this._backgroundAttachment;
```

::: {#setter .section .multi-line-signature}
void backgroundAttachment=([String](../../dart-core/string-class)?
value)

::: {.features}
override
:::
:::

Sets the value of \"background-attachment\"

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set backgroundAttachment(String? value) {
  _backgroundAttachment = value == null ? '' : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/backgroundAttachment.html>
:::
