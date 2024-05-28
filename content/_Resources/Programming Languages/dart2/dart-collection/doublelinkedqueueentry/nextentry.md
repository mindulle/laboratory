[dart:collection](../../dart-collection/dart-collection-library){._links-link}

nextEntry method
================

::: {.section .multi-line-signature}
[DoubleLinkedQueueEntry](../doublelinkedqueueentry-class)\<E\>?
nextEntry()
:::

The next entry, or `null` if there is none.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
DoubleLinkedQueueEntry<E>? nextEntry() => _nextLink;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/DoubleLinkedQueueEntry/nextEntry.html>
:::
