[dart:collection](../../dart-collection/dart-collection-library){._links-link}

addAll method
=============

::: {.section .multi-line-signature}
void addAll(

1.  [Iterable](../../dart-core/iterable-class)\<E\> iterable

)

::: {.features}
override
:::
:::

Adds all elements of `iterable` at the end of the queue. The length of
the queue is extended by the length of `iterable`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addAll(Iterable<E> iterable) {
  for (final E value in iterable) {
    _sentinel._prepend(value, this);
    _elementCount++;
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/DoubleLinkedQueue/addAll.html>
:::
