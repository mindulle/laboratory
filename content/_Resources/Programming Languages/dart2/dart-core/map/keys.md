[dart:core](../../dart-core/dart-core-library){._links-link}

keys property
=============

::: {#getter .section .multi-line-signature}
[Iterable](../iterable-class)\<K\> keys
:::

The keys of [this](../map-class).

The returned iterable has efficient `length` and `contains` operations,
based on [length](length) and [containsKey](containskey) of the map.

The order of iteration is defined by the individual `Map`
implementation, but must be consistent between changes to the map.

Modifying the map while iterating the keys may break the iteration.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Iterable<K> get keys;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Map/keys.html>
:::
