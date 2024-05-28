[dart:html](../../dart-html/dart-html-library){._links-link}

localName property
==================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) localName

::: {.features}
\@Returns(\'String\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Returns('String')
// Non-null for Elements.
String get localName => JS('String', '#', _localName);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/localName.html>
:::
