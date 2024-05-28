[dart:collection](../../dart-collection/dart-collection-library){._links-link}

addEntries method
=================

::: {.section .multi-line-signature}
void addEntries(

1.  [Iterable](../../dart-core/iterable-class)\<[MapEntry](../../dart-core/mapentry-class)\<K,
    V\>\> entries

)

::: {.features}
override
:::
:::

Adds all key/value pairs of `newEntries` to this map.

If a key of `newEntries` is already in this map, the corresponding value
is overwritten.

The operation is equivalent to doing `this[entry.key] = entry.value` for
each [MapEntry](../../dart-core/mapentry-class) of the iterable.

``` {.language-dart data-language="dart"}
final planets = <int, String>{1: 'Mercury', 2: 'Venus',
  3: 'Earth', 4: 'Mars'};
final gasGiants = <int, String>{5: 'Jupiter', 6: 'Saturn'};
final iceGiants = <int, String>{7: 'Uranus', 8: 'Neptune'};
planets.addEntries(gasGiants.entries);
planets.addEntries(iceGiants.entries);
print(planets);
// {1: Mercury, 2: Venus, 3: Earth, 4: Mars, 5: Jupiter, 6: Saturn,
//  7: Uranus, 8: Neptune}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addEntries(Iterable<MapEntry<K, V>> entries) {
  _map.addEntries(entries);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/MapView/addEntries.html>
:::
