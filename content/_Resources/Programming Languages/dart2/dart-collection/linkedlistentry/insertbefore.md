[dart:collection](../../dart-collection/dart-collection-library){._links-link}

insertBefore method
===================

::: {.section .multi-line-signature}
void insertBefore(

1.  E entry

)
:::

Insert an element before this element in this element\'s linked list.

This entry must be in a linked list when this method is called. The
`entry` must not be in a linked list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void insertBefore(E entry) {
  _list!._insertBefore(this as E, entry, updateFirst: true);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/LinkedListEntry/insertBefore.html>
:::
