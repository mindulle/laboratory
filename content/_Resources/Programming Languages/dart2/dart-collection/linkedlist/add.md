[dart:collection](../../dart-collection/dart-collection-library){._links-link}

add method
==========

::: {.section .multi-line-signature}
void add(

1.  E entry

)
:::

Adds `entry` to the end of the linked list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void add(E entry) {
  _insertBefore(_first, entry, updateFirst: false);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/LinkedList/add.html>
:::
