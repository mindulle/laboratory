[dart:collection](../../dart-collection/dart-collection-library){._links-link}

remove method
=============

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) remove(

1.  [Object](../../dart-core/object-class)? o

)

::: {.features}
override
:::
:::

Removes a single instance of `value` from the queue.

Returns `true` if a value was removed, or `false` if the queue contained
no element equal to `value`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool remove(Object? o) {
  _DoubleLinkedQueueEntry<E> entry = _sentinel._nextLink!;
  while (true) {
    var elementEntry = entry._asNonSentinelEntry();
    if (elementEntry == null) return false;
    bool equals = (elementEntry.element == o);
    if (!identical(this, elementEntry._queue)) {
      // Entry must still be in the queue.
      throw ConcurrentModificationError(this);
    }
    if (equals) {
      entry._remove();
      _elementCount--;
      return true;
    }
    entry = entry._nextLink!;
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/DoubleLinkedQueue/remove.html>
:::
