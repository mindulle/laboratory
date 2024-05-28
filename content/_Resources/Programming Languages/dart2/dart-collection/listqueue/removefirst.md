[dart:collection](../../dart-collection/dart-collection-library){._links-link}

removeFirst method
==================

::: {.section .multi-line-signature}
E removeFirst()

::: {.features}
override
:::
:::

Removes and returns the first element of this queue.

The queue must not be empty when this method is called.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
E removeFirst() {
  if (_head == _tail) throw IterableElementError.noElement();
  _modificationCount++;
  E result = _table[_head] as E;
  _table[_head] = null;
  _head = (_head + 1) & (_table.length - 1);
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListQueue/removeFirst.html>
:::
