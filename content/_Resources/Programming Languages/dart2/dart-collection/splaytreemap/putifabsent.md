[dart:collection](../../dart-collection/dart-collection-library){._links-link}

putIfAbsent method
==================

::: {.section .multi-line-signature}
V putIfAbsent(

1.  K key,
2.  V ifAbsent( )

)

::: {.features}
override
:::
:::

Look up the value of `key`, or add a new entry if it isn\'t there.

Returns the value associated to `key`, if there is one. Otherwise calls
`ifAbsent` to get a new value, associates `key` to that value, and then
returns the new value.

``` {.language-dart data-language="dart"}
final diameters = <num, String>{1.0: 'Earth'};
final otherDiameters = <double, String>{0.383: 'Mercury', 0.949: 'Venus'};

for (final item in otherDiameters.entries) {
  diameters.putIfAbsent(item.key, () => item.value);
}
print(diameters); // {1.0: Earth, 0.383: Mercury, 0.949: Venus}

// If the key already exists, the current value is returned.
final result = diameters.putIfAbsent(0.383, () => 'Random');
print(result); // Mercury
print(diameters); // {1.0: Earth, 0.383: Mercury, 0.949: Venus}
```

Calling `ifAbsent` must not add or remove keys from the map.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
V putIfAbsent(K key, V ifAbsent()) {
  int comp = _splay(key);
  if (comp == 0) {
    return _root!.value;
  }
  int modificationCount = _modificationCount;
  int splayCount = _splayCount;
  V value = ifAbsent();
  if (modificationCount != _modificationCount) {
    throw ConcurrentModificationError(this);
  }
  if (splayCount != _splayCount) {
    comp = _splay(key);
    // Key is still not there, otherwise _modificationCount would be changed.
    assert(comp != 0);
  }
  _addNewRoot(_SplayTreeMapNode(key, value), comp);
  return value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeMap/putIfAbsent.html>
:::
