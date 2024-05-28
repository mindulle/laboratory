[dart:collection](../../dart-collection/dart-collection-library){._links-link}

addAll method
=============

::: {.section .multi-line-signature}
void addAll(

1.  [Iterable](../../dart-core/iterable-class)\<E\> entries

)
:::

Adds `entries` to the end of the linked list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addAll(Iterable<E> entries) {
  entries.forEach(add);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/LinkedList/addAll.html>
:::
