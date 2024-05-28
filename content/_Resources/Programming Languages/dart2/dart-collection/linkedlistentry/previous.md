[dart:collection](../../dart-collection/dart-collection-library){._links-link}

previous property
=================

::: {#getter .section .multi-line-signature}
E? previous
:::

The predecessor of this element in its linked list.

The value is `null` if there is no predecessor in the linked list, or if
this entry is not currently in any list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
E? get previous {
  if (_list == null || identical(this, _list!.first)) return null;
  return _previous;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/LinkedListEntry/previous.html>
:::
