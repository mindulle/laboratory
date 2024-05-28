[dart:collection](../../dart-collection/dart-collection-library){._links-link}

ListQueue\<E\>.of constructor
=============================

::: {.section .multi-line-signature}
ListQueue\<E\>.of(

1.  [Iterable](../../dart-core/iterable-class)\<E\> elements

)
:::

Create a `ListQueue` from `elements`.

The elements are added to the queue, as by [addLast](addlast), in the
order given by `elements.iterator`. Example:

``` {.language-dart data-language="dart"}
final baseQueue = ListQueue.of([1.0, 2.0, 3.0]); // A ListQueue<double>
final numQueue = ListQueue<num>.of(baseQueue);
print(numQueue); // {1.0, 2.0, 3.0}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory ListQueue.of(Iterable<E> elements) =>
    ListQueue<E>()..addAll(elements);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListQueue/ListQueue.of.html>
:::
