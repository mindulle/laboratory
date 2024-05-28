[dart:collection](../../dart-collection/dart-collection-library){._links-link}

lastEntry method
================

::: {.section .multi-line-signature}
[DoubleLinkedQueueEntry](../doublelinkedqueueentry-class)\<E\>?
lastEntry()
:::

The entry object of the last element in the queue.

Each element of the queue has an associated
[DoubleLinkedQueueEntry](../doublelinkedqueueentry-class).

Returns the entry object corresponding to the last element of the queue,
or `null` if the queue is empty.

The entry objects can also be accessed using [firstEntry](firstentry),
and they can be iterated using
[DoubleLinkedQueueEntry.nextEntry](../doublelinkedqueueentry/nextentry)
and
[DoubleLinkedQueueEntry.previousEntry](../doublelinkedqueueentry/previousentry).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
DoubleLinkedQueueEntry<E>? lastEntry() =>
    _sentinel._previousLink!._asNonSentinelEntry();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/DoubleLinkedQueue/lastEntry.html>
:::
