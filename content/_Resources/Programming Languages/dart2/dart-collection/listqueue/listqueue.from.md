[dart:collection](../../dart-collection/dart-collection-library){._links-link}

ListQueue\<E\>.from constructor
===============================

::: {.section .multi-line-signature}
ListQueue\<E\>.from(

1.  [Iterable](../../dart-core/iterable-class) elements

)
:::

Create a `ListQueue` containing all `elements`.

The elements are added to the queue, as by [addLast](addlast), in the
order given by `elements.iterator`.

All the `elements` should be instances of `E`. The `elements` iterable
itself may have any element type, so this constructor can be used to
down-cast a `Queue`, for example as:

``` {.language-dart data-language="dart"}
Queue<SuperType> superQueue = ...;
Queue<SubType> subQueue =
    ListQueue<SubType>.from(superQueue.whereType<SubType>());
```

Example:

``` {.language-dart data-language="dart"}
final numbers = <num>[10, 20, 30];
final queue = ListQueue<int>.from(numbers);
print(queue); // {10, 20, 30}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory ListQueue.from(Iterable<dynamic> elements) {
  if (elements is List<dynamic>) {
    int length = elements.length;
    ListQueue<E> queue = ListQueue<E>(length + 1);
    assert(queue._table.length > length);
    for (int i = 0; i < length; i++) {
      queue._table[i] = elements[i] as E;
    }
    queue._tail = length;
    return queue;
  } else {
    int capacity = _INITIAL_CAPACITY;
    if (elements is EfficientLengthIterable) {
      capacity = elements.length;
    }
    ListQueue<E> result = ListQueue<E>(capacity);
    for (final element in elements) {
      result.addLast(element as E);
    }
    return result;
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListQueue/ListQueue.from.html>
:::
