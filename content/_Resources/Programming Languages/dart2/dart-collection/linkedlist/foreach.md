[dart:collection](../../dart-collection/dart-collection-library){._links-link}

forEach method
==============

::: {.section .multi-line-signature}
void forEach(

1.  void action(
    1.  E entry

    )

)

::: {.features}
override
:::
:::

Call `action` with each entry in this linked list.

It\'s an error if `action` modifies the linked list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void forEach(void action(E entry)) {
  int modificationCount = _modificationCount;
  if (isEmpty) return;

  E current = _first!;
  do {
    action(current);
    if (modificationCount != _modificationCount) {
      throw ConcurrentModificationError(this);
    }
    current = current._next!;
  } while (!identical(current, _first));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/LinkedList/forEach.html>
:::
