[dart:collection](../../dart-collection/dart-collection-library){._links-link}

isNotEmpty property
===================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) isNotEmpty

::: {.features}
override
:::
:::

Whether this collection has at least one element.

May be computed by checking if `iterator.moveNext()` returns `true`.

Example:

``` {.language-dart data-language="dart"}
final numbers = <int>{1, 2, 3};
print(numbers.isNotEmpty); // true;
print(numbers.iterator.moveNext()); // true
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isNotEmpty => !isEmpty;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/IterableMixin/isNotEmpty.html>
:::
