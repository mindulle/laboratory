[dart:core](../../dart-core/dart-core-library){._links-link}

toString method
===============

::: {.section .multi-line-signature}
[String](../string-class) toString()

::: {.features}
override
:::
:::

Returns a [String](../string-class) representation of the stack trace.

The string represents the full stack trace starting from the point where
a throw occurred to the top of the current call sequence.

The exact format of the string representation is not final.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String toString();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/StackTrace/toString.html>
:::
