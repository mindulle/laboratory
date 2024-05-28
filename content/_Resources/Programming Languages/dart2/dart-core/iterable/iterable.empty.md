[dart:core](../../dart-core/dart-core-library){._links-link}

Iterable\<E\>.empty constructor
===============================

::: {.section .multi-line-signature}
const Iterable\<E\>.empty()
:::

Creates an empty iterable.

The empty iterable has no elements, and iterating it always stops
immediately.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const factory Iterable.empty() = EmptyIterable<E>;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Iterable/Iterable.empty.html>
:::
