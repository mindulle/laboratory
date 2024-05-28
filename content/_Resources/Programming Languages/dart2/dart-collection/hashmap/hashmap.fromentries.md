[dart:collection](../../dart-collection/dart-collection-library){._links-link}

HashMap\<K, V\>.fromEntries constructor
=======================================

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.1\")

</div>

HashMap\<K, V\>.fromEntries(

1.  [Iterable](../../dart-core/iterable-class)\<[MapEntry](../../dart-core/mapentry-class)\<K,
    V\>\> entries

)
:::

Creates a [HashMap](../hashmap-class) containing the entries of
`entries`.

Returns a new `HashMap<K, V>` where all entries of `entries` have been
added in iteration order.

If multiple `entries` have the same key, later occurrences overwrite the
earlier ones.

Example:

``` {.language-dart data-language="dart"}
final numbers = [11, 12, 13, 14];
final map = HashMap.fromEntries(numbers.map((i) => MapEntry(i, i * i)));
print(map); // {11: 121, 12: 144, 13: 169, 14: 196}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.1")
factory HashMap.fromEntries(Iterable<MapEntry<K, V>> entries) =>
    HashMap<K, V>()..addEntries(entries);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/HashMap/HashMap.fromEntries.html>
:::
