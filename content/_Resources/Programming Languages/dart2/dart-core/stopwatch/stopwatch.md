[dart:core](../../dart-core/dart-core-library){._links-link}

Stopwatch constructor
=====================

::: {.section .multi-line-signature}
Stopwatch()
:::

Creates a [Stopwatch](../stopwatch-class) in stopped state with a zero
elapsed count.

The following example shows how to start a
[Stopwatch](../stopwatch-class) immediately after allocation.

``` {.language-dart data-language="dart"}
final stopwatch = Stopwatch()..start();
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stopwatch() {
  _frequency; // Ensures initialization before using any method.
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Stopwatch/Stopwatch.html>
:::
