[dart:core](../../dart-core/dart-core-library){._links-link}

addAll method
=============

::: {.section .multi-line-signature}
void addAll(

1.  [Map](../map-class)\<K, V\> other

)
:::

Adds all key/value pairs of `other` to this map.

If a key of `other` is already in this map, its value is overwritten.

The operation is equivalent to doing `this[key] = value` for each key
and associated value in other. It iterates over `other`, which must
therefore not change during the iteration.

``` {.language-dart data-language="dart"}
final planets = <int, String>{1: 'Mercury', 2: 'Earth'};
planets.addAll({5: 'Jupiter', 6: 'Saturn'});
print(planets); // {1: Mercury, 2: Earth, 5: Jupiter, 6: Saturn}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addAll(Map<K, V> other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Map/addAll.html>
:::
