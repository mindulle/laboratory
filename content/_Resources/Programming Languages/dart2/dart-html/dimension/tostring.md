[dart:html](../../dart-html/dart-html-library){._links-link}

toString method
===============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) toString()

::: {.features}
override
:::
:::

Print out the CSS String representation of this value.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String toString() {
  return '${_value}${_unit}';
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Dimension/toString.html>
:::
