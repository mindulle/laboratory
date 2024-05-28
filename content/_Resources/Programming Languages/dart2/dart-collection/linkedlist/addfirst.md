[dart:collection](../../dart-collection/dart-collection-library){._links-link}

addFirst method
===============

::: {.section .multi-line-signature}
void addFirst(

1.  E entry

)
:::

Adds `entry` to the beginning of the linked list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addFirst(E entry) {
  _insertBefore(_first, entry, updateFirst: true);
  _first = entry;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/LinkedList/addFirst.html>
:::
