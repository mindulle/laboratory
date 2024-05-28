[dart:collection](../../dart-collection/dart-collection-library){._links-link}

clear method
============

::: {.section .multi-line-signature}
void clear()
:::

Remove all elements from this linked list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void clear() {
  _modificationCount++;
  if (isEmpty) return;

  E next = _first!;
  do {
    E entry = next;
    next = entry._next!;
    entry._next = entry._previous = entry._list = null;
  } while (!identical(next, _first));

  _first = null;
  _length = 0;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/LinkedList/clear.html>
:::
