[dart:core](../../dart-core/dart-core-library){._links-link}

Map\<K, V\>.fromIterable constructor
====================================

::: {.section .multi-line-signature}
Map\<K, V\>.fromIterable(

1.  [Iterable](../iterable-class) iterable,
2.  {K key(
    1.  dynamic element

    )?,
3.  V value(
    1.  dynamic element

    )?}

)
:::

Creates a Map instance in which the keys and values are computed from
the `iterable`.

For each element of the `iterable`, a key/value pair is computed by
applying `key` and `value` respectively to the element of the iterable.

Equivalent to the map literal:

``` {.language-dart data-language="dart"}
<K, V>{for (var v in iterable) key(v): value(v)}
```

The literal is generally preferable because it allows for a more precise
typing.

The example below creates a new map from a list of integers. The keys of
`map` are the `list` values converted to strings, and the values of the
`map` are the squares of the `list` values:

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3];
final map = Map<String, int>.fromIterable(numbers,
    key: (item) => item.toString(),
    value: (item) => item * item);
print(map); // {1: 1, 2: 4, 3: 9}
```

If no values are specified for `key` and `value`, the default is the
identity function. In that case, the iterable element must be assignable
to the key or value type of the created map.

In the following example, the keys and corresponding values of `map` are
the `list` values directly:

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3];
final map = Map.fromIterable(numbers);
print(map); // {1: 1, 2: 2, 3: 3}
```

The keys computed by the source `iterable` do not need to be unique. The
last occurrence of a key will overwrite the value of any previous
occurrence.

The created map is a
[LinkedHashMap](../../dart-collection/linkedhashmap-class). A
`LinkedHashMap` requires the keys to implement compatible `operator==`
and `hashCode`. It iterates in key insertion order.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Map.fromIterable(Iterable iterable,
    {K key(dynamic element)?,
    V value(dynamic element)?}) = LinkedHashMap<K, V>.fromIterable;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Map/Map.fromIterable.html>
:::
