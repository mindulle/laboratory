[dart:core](../../dart-core/dart-core-library){._links-link}

empty constant
==============

::: {.section .multi-line-signature}
\_StringStackTrace const empty

::: {.features}
\@Since(\"2.8\")
:::
:::

A stack trace object with no information.

This stack trace is used as the default in situations where a stack
trace is required, but the user has not supplied one.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.8")
static const empty = const _StringStackTrace("");
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/StackTrace/empty-constant.html>
:::
