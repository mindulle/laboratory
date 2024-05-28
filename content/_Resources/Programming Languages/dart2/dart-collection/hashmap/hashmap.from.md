[dart:collection](../../dart-collection/dart-collection-library){._links-link}

HashMap\<K, V\>.from constructor
================================

::: {.section .multi-line-signature}
HashMap\<K, V\>.from(

1.  [Map](../../dart-core/map-class) other

)
:::

Creates a [HashMap](../hashmap-class) that contains all key/value pairs
of `other`.

The keys must all be instances of `K` and the values of `V`. The `other`
map itself can have any type.

``` {.language-dart data-language="dart"}
final baseMap = {1: 'A', 2: 'B', 3: 'C'};
final fromBaseMap = HashMap<int, String>.from(baseMap);
print(fromBaseMap); // {1: A, 2: B, 3: C}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory HashMap.from(Map<dynamic, dynamic> other) {
  HashMap<K, V> result = HashMap<K, V>();
  other.forEach((dynamic k, dynamic v) {
    result[k as K] = v as V;
  });
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/HashMap/HashMap.from.html>
:::
