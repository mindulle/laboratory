[dart:html](../../dart-html/dart-html-library){._links-link}

toString method
===============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) toString()
:::

Print out a String representation of this Node.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String toString() {
  String? value = nodeValue; // Fetch DOM Node property once.
  return value == null ? super.toString() : value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Node/toString.html>
:::
