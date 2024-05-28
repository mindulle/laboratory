[dart:core](../../dart-core/dart-core-library){._links-link}

toString method
===============

::: {.section .multi-line-signature}
[String](../string-class) toString()

::: {.features}
override
:::
:::

Returns a string which represents the underlying type.

The string is only intended for providing information to a reader while
debugging. There is no guaranteed format, the string value returned for
a [Type](../type-class) instances is entirely implementation dependent.

The string should be consistent, so a `Type` object for the *same* type
returns the same string throughout a program execution. The string may
or may not contain parts corresponding to the source name of declaration
of the type, if the type has a source name at all (some types reachable
through `dart:mirrors` may not).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String toString();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Type/toString.html>
:::
