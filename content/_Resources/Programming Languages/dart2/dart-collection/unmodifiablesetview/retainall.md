[dart:collection](../../dart-collection/dart-collection-library){._links-link}

retainAll method
================

::: {.section .multi-line-signature}
void retainAll(

1.  [Iterable](../../dart-core/iterable-class)\<[Object](../../dart-core/object-class)?\>
    elements

)

::: {.features}
inherited
:::
:::

This operation is not supported by an unmodifiable set.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void retainAll(Iterable<Object?> elements) => _throwUnmodifiable();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/UnmodifiableSetView/retainAll.html>
:::
