[dart:collection](../../dart-collection/dart-collection-library){._links-link}

DoubleLinkedQueue\<E\>.from constructor
=======================================

::: {.section .multi-line-signature}
DoubleLinkedQueue\<E\>.from(

1.  [Iterable](../../dart-core/iterable-class) elements

)
:::

Creates a double-linked queue containing all `elements`.

The element order in the queue is as if the elements were added using
[addLast](addlast) in the order provided by `elements`.iterator.

All the `elements` should be instances of `E`. The `elements` iterable
itself may have any element type, so this constructor can be used to
down-cast a [Queue](../queue-class), for example as:

``` {.language-dart data-language="dart"}
Queue<SuperType> superQueue = ...;
Queue<SubType> subQueue =
    DoubleLinkedQueue<SubType>.from(superQueue.whereType<SubType>());
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory DoubleLinkedQueue.from(Iterable<dynamic> elements) {
  DoubleLinkedQueue<E> list = DoubleLinkedQueue<E>();
  for (final e in elements) {
    list.addLast(e as E);
  }
  return list;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/DoubleLinkedQueue/DoubleLinkedQueue.from.html>
:::
