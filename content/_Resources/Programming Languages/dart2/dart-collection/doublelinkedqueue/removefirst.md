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
  // Hits sentinel's `_remove` if queue is empty.
  E result = _sentinel._nextLink!._remove();
  _elementCount--;
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/DoubleLinkedQueue/removeFirst.html>
:::
