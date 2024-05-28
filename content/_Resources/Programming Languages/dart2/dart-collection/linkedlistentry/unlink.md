[dart:collection](../../dart-collection/dart-collection-library){._links-link}

unlink method
=============

::: {.section .multi-line-signature}
void unlink()
:::

Unlink the element from its linked list.

The entry must currently be in a linked list when this method is called.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void unlink() {
  _list!._unlink(this as E);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/LinkedListEntry/unlink.html>
:::
