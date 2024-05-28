[dart:collection](../../dart-collection/dart-collection-library){._links-link}

DoubleLinkedQueue\<E\>.of constructor
=====================================

::: {.section .multi-line-signature}
DoubleLinkedQueue\<E\>.of(

1.  [Iterable](../../dart-core/iterable-class)\<E\> elements

)
:::

Creates a double-linked queue from `elements`.

The element order in the queue is as if the elements were added using
[addLast](addlast) in the order provided by `elements`.iterator.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory DoubleLinkedQueue.of(Iterable<E> elements) =>
    DoubleLinkedQueue<E>()..addAll(elements);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/DoubleLinkedQueue/DoubleLinkedQueue.of.html>
:::
