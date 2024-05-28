[dart:collection](../../dart-collection/dart-collection-library){._links-link}

next property
=============

::: {#getter .section .multi-line-signature}
E? next
:::

The successor of this element in its linked list.

The value is `null` if there is no successor in the linked list, or if
this entry is not currently in any list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
E? get next {
  if (_list == null || identical(_list!.first, _next)) return null;
  return _next;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/LinkedListEntry/next.html>
:::
