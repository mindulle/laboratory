[dart:collection](../../dart-collection/dart-collection-library){._links-link}

asMap method
============

::: {.section .multi-line-signature}
[Map](../../dart-core/map-class)\<[int](../../dart-core/int-class), E\>
asMap()

::: {.features}
override
:::
:::

An unmodifiable [Map](../../dart-core/map-class) view of this list.

The map uses the indices of this list as keys and the corresponding
objects as values. The `Map.keys`
[Iterable](../../dart-core/iterable-class) iterates the indices of this
list in numerical order.

``` {.language-dart data-language="dart"}
var words = <String>['fee', 'fi', 'fo', 'fum'];
var map = words.asMap();  // {0: fee, 1: fi, 2: fo, 3: fum}
map.keys.toList(); // [0, 1, 2, 3]
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Map<int, E> asMap() {
  return ListMapView<E>(this);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListMixin/asMap.html>
:::
