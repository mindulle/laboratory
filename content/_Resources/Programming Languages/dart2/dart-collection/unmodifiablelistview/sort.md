[dart:collection](../../dart-collection/dart-collection-library){._links-link}

sort method
===========

::: {.section .multi-line-signature}
void sort(

1.  \[[Comparator](../../dart-core/comparator)\<E\>? compare\]

)

::: {.features}
inherited
:::
:::

This operation is not supported by an unmodifiable list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void sort([Comparator<E>? compare]) {
  throw new UnsupportedError("Cannot modify an unmodifiable list");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/UnmodifiableListView/sort.html>
:::
