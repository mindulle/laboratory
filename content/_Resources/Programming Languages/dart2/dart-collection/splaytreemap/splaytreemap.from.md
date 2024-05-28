[dart:collection](../../dart-collection/dart-collection-library){._links-link}

SplayTreeMap\<K, V\>.from constructor
=====================================

::: {.section .multi-line-signature}
SplayTreeMap\<K, V\>.from(

1.  [Map](../../dart-core/map-class) other,
2.  \[[int](../../dart-core/int-class) compare(
    1.  K key1,
    2.  K key2

    )?,
3.  [bool](../../dart-core/bool-class) isValidKey(
    1.  dynamic potentialKey

    )?\]

)
:::

Creates a [SplayTreeMap](../splaytreemap-class) that contains all
key/value pairs of `other`.

The keys must all be instances of `K` and the values of `V`. The `other`
map itself can have any type. Example:

``` {.language-dart data-language="dart"}
final baseMap = <int, Object>{3: 'C', 1: 'A', 2: 'B'};
final fromBaseMap = SplayTreeMap<int, String>.from(baseMap);
print(fromBaseMap); // {1: A, 2: B, 3: C}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory SplayTreeMap.from(Map<dynamic, dynamic> other,
    [int Function(K key1, K key2)? compare,
    bool Function(dynamic potentialKey)? isValidKey]) {
  if (other is Map<K, V>) {
    return SplayTreeMap<K, V>.of(other, compare, isValidKey);
  }
  SplayTreeMap<K, V> result = SplayTreeMap<K, V>(compare, isValidKey);
  other.forEach((dynamic k, dynamic v) {
    result[k] = v;
  });
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeMap/SplayTreeMap.from.html>
:::
