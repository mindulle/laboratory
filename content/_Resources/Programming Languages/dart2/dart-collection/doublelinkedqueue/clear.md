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
  var cursor = _sentinel._nextLink!;
  while (true) {
    var entry = cursor._asNonSentinelEntry();
    if (entry == null) break;
    cursor = cursor._nextLink!;
    entry
      .._nextLink = null
      .._previousLink = null
      .._queue = null;
  }
  _sentinel._nextLink = _sentinel;
  _sentinel._previousLink = _sentinel;
  _elementCount = 0;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/DoubleLinkedQueue/clear.html>
:::
