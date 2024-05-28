[dart:collection](../../dart-collection/dart-collection-library){._links-link}

forEachEntry method
===================

::: {.section .multi-line-signature}
void forEachEntry(

1.  void action(
    1.  [DoubleLinkedQueueEntry](../doublelinkedqueueentry-class)\<E\>
        element

    )

)
:::

Calls `action` for each entry object of this double-linked queue.

Each element of the queue has an associated
[DoubleLinkedQueueEntry](../doublelinkedqueueentry-class). This method
iterates the entry objects from first to last and calls `action` with
each object in turn.

The entry objects can also be accessed using [firstEntry](firstentry)
and [lastEntry](lastentry), and iterated using
[DoubleLinkedQueueEntry.nextEntry()](../doublelinkedqueueentry/nextentry)
and
[DoubleLinkedQueueEntry.previousEntry()](../doublelinkedqueueentry/previousentry).

The `action` function can use methods on
[DoubleLinkedQueueEntry](../doublelinkedqueueentry-class) to remove the
entry or it can insert elements before or after the entry. If the
current entry is removed, iteration continues with the entry that was
following the current entry when `action` was called. Any elements
inserted after the current element before it is removed will not be
visited by the iteration.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void forEachEntry(void action(DoubleLinkedQueueEntry<E> element)) {
  var cursor = _sentinel._nextLink!;
  while (true) {
    var element = cursor._asNonSentinelEntry();
    if (element == null) break;
    if (!identical(element._queue, this)) {
      throw ConcurrentModificationError(this);
    }
    cursor = cursor._nextLink!;
    // Remember both element and element._nextLink (as cursor).
    // If someone calls `element.remove()` we continue from `next`.
    // Otherwise we use the value of element._nextLink which may have been
    // updated.
    action(element);
    if (identical(this, element._queue)) {
      cursor = element._nextLink!;
    }
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/DoubleLinkedQueue/forEachEntry.html>
:::
