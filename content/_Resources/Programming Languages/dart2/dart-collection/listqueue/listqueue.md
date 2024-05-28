[dart:collection](../../dart-collection/dart-collection-library){._links-link}

ListQueue\<E\> constructor
==========================

::: {.section .multi-line-signature}
ListQueue\<E\>(

1.  \[[int](../../dart-core/int-class)? initialCapacity\]

)
:::

Create an empty queue.

If `initialCapacity` is given, prepare the queue for at least that many
elements.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ListQueue([int? initialCapacity])
    : _head = 0,
      _tail = 0,
      _table = List<E?>.filled(_calculateCapacity(initialCapacity), null);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListQueue/ListQueue.html>
:::
