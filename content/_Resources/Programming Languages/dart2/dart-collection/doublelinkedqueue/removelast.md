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
  // Hits sentinel's `_remove` if queue is empty.
  E result = _sentinel._previousLink!._remove();
  _elementCount--;
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/DoubleLinkedQueue/removeLast.html>
:::
