[dart:collection](../../dart-collection/dart-collection-library){._links-link}

removeLast method
=================

::: {.section .multi-line-signature}
E removeLast()

::: {.features}
override
:::
:::

Removes and returns the last element of the queue.

The queue must not be empty when this method is called.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
E removeLast() {
  if (_head == _tail) throw IterableElementError.noElement();
  _modificationCount++;
  _tail = (_tail - 1) & (_table.length - 1);
  E result = _table[_tail] as E;
  _table[_tail] = null;
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListQueue/removeLast.html>
:::
