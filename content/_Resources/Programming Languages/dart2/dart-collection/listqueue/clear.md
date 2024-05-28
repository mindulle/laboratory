[dart:collection](../../dart-collection/dart-collection-library){._links-link}

clear method
============

::: {.section .multi-line-signature}
void clear()

::: {.features}
override
:::
:::

Removes all elements in the queue. The size of the queue becomes zero.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void clear() {
  if (_head != _tail) {
    for (int i = _head; i != _tail; i = (i + 1) & (_table.length - 1)) {
      _table[i] = null;
    }
    _head = _tail = 0;
    _modificationCount++;
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListQueue/clear.html>
:::
