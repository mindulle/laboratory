[dart:collection](../../dart-collection/dart-collection-library){._links-link}

addAll method
=============

::: {.section .multi-line-signature}
void addAll(

1.  [Iterable](../../dart-core/iterable-class)\<E\> elements

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
void addAll(Iterable<E> elements) {
  if (elements is List<E>) {
    List<E> list = elements;
    int addCount = list.length;
    int length = this.length;
    if (length + addCount >= _table.length) {
      _preGrow(length + addCount);
      // After preGrow, all elements are at the start of the list.
      _table.setRange(length, length + addCount, list, 0);
      _tail += addCount;
    } else {
      // Adding addCount elements won't reach _head.
      int endSpace = _table.length - _tail;
      if (addCount < endSpace) {
        _table.setRange(_tail, _tail + addCount, list, 0);
        _tail += addCount;
      } else {
        int preSpace = addCount - endSpace;
        _table.setRange(_tail, _tail + endSpace, list, 0);
        _table.setRange(0, preSpace, list, endSpace);
        _tail = preSpace;
      }
    }
    _modificationCount++;
  } else {
    for (E element in elements) _add(element);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListQueue/addAll.html>
:::
