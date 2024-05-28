[dart:core](../../dart-core/dart-core-library){._links-link}

Map\<K, V\>.from constructor
============================

::: {.section .multi-line-signature}
Map\<K, V\>.from(

1.  [Map](../map-class) other

)
:::

Creates a [LinkedHashMap](../../dart-collection/linkedhashmap-class)
with the same keys and values as `other`.

The keys must all be instances of `K` and the values of `V`. The `other`
map itself can have any type, unlike for [Map.of](map.of), and the key
and value types are checked (and can fail) at run-time.

Prefer using [Map.of](map.of) when possible, and only use `Map.from` to
create a new map with more precise types than the original, and when
it\'s known that all the keys and values have those more precise types.

A `LinkedHashMap` requires the keys to implement compatible `operator==`
and `hashCode`. It iterates in key insertion order.

``` {.language-dart data-language="dart"}
final planets = <num, String>{1: 'Mercury', 2: 'Venus', 3: 'Earth', 4: 'Mars'};
final mapFrom = Map<int, String>.from(planets);
print(mapFrom); // {1: Mercury, 2: Venus, 3: Earth, 4: Mars}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Map.from(Map other) = LinkedHashMap<K, V>.from;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Map/Map.from.html>
:::
