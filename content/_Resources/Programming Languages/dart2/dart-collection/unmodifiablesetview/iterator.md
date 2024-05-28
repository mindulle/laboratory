[dart:collection](../../dart-collection/dart-collection-library){._links-link}

iterator property
=================

::: {#getter .section .multi-line-signature}
[Iterator](../../dart-core/iterator-class)\<E\> iterator

::: {.features}
override
:::
:::

An iterator that iterates over the elements of this set.

The order of iteration is defined by the individual `Set`
implementation, but must be consistent between changes to the set.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Iterator<E> get iterator => _source.iterator;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/UnmodifiableSetView/iterator.html>
:::
