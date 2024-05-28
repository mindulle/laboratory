[dart:core](../../dart-core/dart-core-library){._links-link}

operator \[\] method
====================

::: {.section .multi-line-signature}
E operator \[\](

1.  [int](../int-class) index

)
:::

The object at the given `index` in the list.

The `index` must be a valid index of this list, which means that `index`
must be non-negative and less than [length](length).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
E operator [](int index);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/operator_get.html>
:::
