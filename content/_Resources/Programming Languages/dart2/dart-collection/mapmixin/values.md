[dart:collection](../../dart-collection/dart-collection-library){._links-link}

values property
===============

::: {#getter .section .multi-line-signature}
[Iterable](../../dart-core/iterable-class)\<V\> values

::: {.features}
override
:::
:::

The values of [this](../mapmixin-class).

The values are iterated in the order of their corresponding keys. This
means that iterating [keys](keys) and [values](values) in parallel will
provide matching pairs of keys and values.

The returned iterable has an efficient `length` method based on the
[length](length) of the map. Its
[Iterable.contains](../../dart-core/iterable/contains) method is based
on `==` comparison.

Modifying the map while iterating the values may break the iteration.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Iterable<V> get values => _MapBaseValueIterable<K, V>(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/MapMixin/values.html>
:::
