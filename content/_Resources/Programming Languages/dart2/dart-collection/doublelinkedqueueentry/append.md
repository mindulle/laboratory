[dart:collection](../../dart-collection/dart-collection-library){._links-link}

append method
=============

::: {.section .multi-line-signature}
void append(

1.  E e

)
:::

Appends the given element `e` as entry just after this entry.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void append(E e) {
  DoubleLinkedQueueEntry<E>(e)._link(this, _nextLink);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/DoubleLinkedQueueEntry/append.html>
:::
