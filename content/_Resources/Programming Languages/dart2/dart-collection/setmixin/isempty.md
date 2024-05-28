[dart:collection](../../dart-collection/dart-collection-library){._links-link}

isEmpty property
================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) isEmpty

::: {.features}
override
:::
:::

Whether this collection has no elements.

May be computed by checking if `iterator.moveNext()` returns `false`.

Example:

``` {.language-dart data-language="dart"}
final emptyList = <int>[];
print(emptyList.isEmpty); // true;
print(emptyList.iterator.moveNext()); // false
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isEmpty => length == 0;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SetMixin/isEmpty.html>
:::
