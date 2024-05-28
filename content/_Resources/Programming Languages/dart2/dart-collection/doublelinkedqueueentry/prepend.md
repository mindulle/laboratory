[dart:collection](../../dart-collection/dart-collection-library){._links-link}

prepend method
==============

::: {.section .multi-line-signature}
void prepend(

1.  E e

)
:::

Prepends the given `e` as entry just before this entry.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void prepend(E e) {
  DoubleLinkedQueueEntry<E>(e)._link(_previousLink, this);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/DoubleLinkedQueueEntry/prepend.html>
:::
