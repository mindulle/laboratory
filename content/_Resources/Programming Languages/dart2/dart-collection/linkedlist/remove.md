[dart:collection](../../dart-collection/dart-collection-library){._links-link}

remove method
=============

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) remove(

1.  E entry

)
:::

Removes `entry` from the linked list.

Returns false and does nothing if `entry` is not in this linked list.

This is equivalent to calling `entry.unlink()` if the entry is in this
list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool remove(E entry) {
  if (entry._list != this) return false;
  _unlink(entry); // Unlink will decrement length.
  return true;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/LinkedList/remove.html>
:::
