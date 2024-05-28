[dart:core](../../dart-core/dart-core-library){._links-link}

Map\<K, V\>.fromEntries constructor
===================================

::: {.section .multi-line-signature}
Map\<K, V\>.fromEntries(

1.  [Iterable](../iterable-class)\<[MapEntry](../mapentry-class)\<K,
    V\>\> entries

)
:::

Creates a new map and adds all entries.

Returns a new `Map<K, V>` where all entries of `entries` have been added
in iteration order.

If multiple `entries` have the same key, later occurrences overwrite the
value of the earlier ones.

Equivalent to the map literal:

``` {.language-dart data-language="dart"}
<K, V>{for (var e in entries) e.key: e.value}
```

Example:

``` {.language-dart data-language="dart"}
final moonCount = <String, int>{'Mercury': 0, 'Venus': 0, 'Earth': 1,
  'Mars': 2, 'Jupiter': 79, 'Saturn': 82, 'Uranus': 27, 'Neptune': 14};
final map = Map.fromEntries(moonCount.entries);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Map.fromEntries(Iterable<MapEntry<K, V>> entries) =>
    <K, V>{}..addEntries(entries);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Map/Map.fromEntries.html>
:::
