[dart:collection](../../dart-collection/dart-collection-library){._links-link}

reversed property
=================

::: {#getter .section .multi-line-signature}
[Iterable](../../dart-core/iterable-class)\<E\> reversed

::: {.features}
override
:::
:::

An [Iterable](../../dart-core/iterable-class) of the objects in this
list in reverse order.

``` {.language-dart data-language="dart"}
final numbers = <String>['two', 'three', 'four'];
final reverseOrder = numbers.reversed;
print(reverseOrder.toList()); // [four, three, two]
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Iterable<E> get reversed => ReversedListIterable<E>(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListMixin/reversed.html>
:::
