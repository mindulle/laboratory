[dart:collection](../../dart-collection/dart-collection-library){._links-link}

update method
=============

::: {.section .multi-line-signature}
V update(

1.  K key,
2.  V update(
    1.  V value

    ),
3.  {V ifAbsent( )?}

)

::: {.features}
override
:::
:::

Updates the value for the provided `key`.

Returns the new value associated with the key.

If the key is present, invokes [update](update) with the current value
and stores the new value in the map.

If the key is not present and `ifAbsent` is provided, calls `ifAbsent`
and adds the key with the returned value to the map.

If the key is not present, `ifAbsent` must be provided.

``` {.language-dart data-language="dart"}
final planetsFromSun = <int, String>{1: 'Mercury', 2: 'unknown',
  3: 'Earth'};
// Update value for known key value 2.
planetsFromSun.update(2, (value) => 'Venus');
print(planetsFromSun); // {1: Mercury, 2: Venus, 3: Earth}

final largestPlanets = <int, String>{1: 'Jupiter', 2: 'Saturn',
  3: 'Neptune'};
// Key value 8 is missing from list, add it using [ifAbsent].
largestPlanets.update(8, (value) => 'New', ifAbsent: () => 'Mercury');
print(largestPlanets); // {1: Jupiter, 2: Saturn, 3: Neptune, 8: Mercury}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
V update(K key, V update(V value), {V Function()? ifAbsent}) {
  var comp = _splay(key);
  if (comp == 0) {
    var modificationCount = _modificationCount;
    var splayCount = _splayCount;
    var newValue = update(_root!.value);
    if (modificationCount != _modificationCount) {
      throw ConcurrentModificationError(this);
    }
    if (splayCount != _splayCount) {
      _splay(key);
    }
    _root = _root!._replaceValue(newValue);
    _splayCount += 1;
    return newValue;
  }
  if (ifAbsent != null) {
    var modificationCount = _modificationCount;
    var splayCount = _splayCount;
    var newValue = ifAbsent();
    if (modificationCount != _modificationCount) {
      throw ConcurrentModificationError(this);
    }
    if (splayCount != _splayCount) {
      comp = _splay(key);
    }
    _addNewRoot(_SplayTreeMapNode(key, newValue), comp);
    return newValue;
  }
  throw ArgumentError.value(key, "key", "Key not in map.");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeMap/update.html>
:::
