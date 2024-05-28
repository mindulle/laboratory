[dart:collection](../../dart-collection/dart-collection-library){._links-link}

remove method
=============

::: {.section .multi-line-signature}
E remove()
:::

Removes this entry from any chain of entries it is part of.

Returns its element value.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
E remove() {
  _previousLink?._nextLink = _nextLink;
  _nextLink?._previousLink = _previousLink;
  _nextLink = null;
  _previousLink = null;
  return element;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/DoubleLinkedQueueEntry/remove.html>
:::
