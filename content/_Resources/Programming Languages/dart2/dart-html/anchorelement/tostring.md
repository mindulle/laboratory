[dart:html](../../dart-html/dart-html-library){._links-link}

toString method
===============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) toString()

::: {.features}
override
:::
:::

The string representation of this element.

This is equivalent to reading the [localName](../element/localname)
property.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String toString() => JS('String', 'String(#)', this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/AnchorElement/toString.html>
:::
