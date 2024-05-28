[dart:collection](../../dart-collection/dart-collection-library){._links-link}

forEach method
==============

::: {.section .multi-line-signature}
void forEach(

1.  void f(
    1.  E element

    )

)
:::

Invokes `action` on each element of this iterable in iteration order.

Example:

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 6, 7];
numbers.forEach(print);
// 1
// 2
// 6
// 7
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void forEach(void f(E element)) {
  int modificationCount = _modificationCount;
  for (int i = _head; i != _tail; i = (i + 1) & (_table.length - 1)) {
    f(_table[i] as E);
    _checkModification(modificationCount);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListQueue/forEach.html>
:::
