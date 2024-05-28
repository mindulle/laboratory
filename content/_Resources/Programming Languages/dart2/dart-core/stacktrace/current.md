[dart:core](../../dart-core/dart-core-library){._links-link}

current property
================

::: {#getter .section .multi-line-signature}
[StackTrace](../stacktrace-class) current
:::

Returns a representation of the current stack trace.

This is similar to what can be achieved by doing:

``` {.language-dart data-language="dart"}
try { throw 0; } catch (_, stack) { return stack; }
```

The getter achieves this without throwing if possible.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static StackTrace get current;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/StackTrace/current.html>
:::
