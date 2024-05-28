[dart:core](../../dart-core/dart-core-library){._links-link}

toString method
===============

::: {.section .multi-line-signature}
[String](../string-class) toString()

::: {.features}
override
:::
:::

Returns either `"true"` for `true` and `"false"` for `false`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String toString() {
  return this ? "true" : "false";
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/bool/toString.html>
:::
