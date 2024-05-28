[dart:collection](../../dart-collection/dart-collection-library){._links-link}

containsKey method
==================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) containsKey(

1.  [Object](../../dart-core/object-class)? key

)

::: {.features}
override
:::
:::

Whether this map contains the given `key`.

Returns true if any of the keys in the map are equal to `key` according
to the equality used by the map.

``` {.language-dart data-language="dart"}
final moonCount = <String, int>{'Mercury': 0, 'Venus': 0, 'Earth': 1,
  'Mars': 2, 'Jupiter': 79, 'Saturn': 82, 'Uranus': 27, 'Neptune': 14 };
final containsUranus = moonCount.containsKey('Uranus'); // true
final containsPluto = moonCount.containsKey('Pluto'); // false
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool containsKey(Object? key) => _containsKey(key);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeMap/containsKey.html>
:::
