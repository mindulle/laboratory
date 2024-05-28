[dart:io](../../dart-io/dart-io-library){._links-link}

stderr property
===============

::: {.section .multi-line-signature}
dynamic stderr

::: {.features}
final
:::
:::

Standard error from the process. The value used for the `stderrEncoding`
argument to `Process.run` determines the type. If `null` was used, this
value is of type `List<int>` otherwise it is of type `String`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final stderr;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ProcessResult/stderr.html>
:::
