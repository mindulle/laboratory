[dart:collection](../../dart-collection/dart-collection-library){._links-link}

removeAt method
===============

::: {.section .multi-line-signature}
E removeAt(

1.  [int](../../dart-core/int-class) index

)

::: {.features}
inherited
:::
:::

This operation is not supported by an unmodifiable list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
E removeAt(int index) {
  throw new UnsupportedError("Cannot remove from an unmodifiable list");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/UnmodifiableListView/removeAt.html>
:::
