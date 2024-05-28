[dart:collection](../../dart-collection/dart-collection-library){._links-link}

retainWhere method
==================

::: {.section .multi-line-signature}
void retainWhere(

1.  [bool](../../dart-core/bool-class) test(
    1.  E element

    )

)

::: {.features}
override
:::
:::

Removes all elements not matched by `test` from the queue.

The `test` function must not throw or modify the queue.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void retainWhere(bool test(E element)) {
  _filter(test, false);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/DoubleLinkedQueue/retainWhere.html>
:::
