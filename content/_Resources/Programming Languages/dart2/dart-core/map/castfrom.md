[dart:core](../../dart-core/dart-core-library){._links-link}

castFrom\<K, V, K2, V2\> method
===============================

::: {.section .multi-line-signature}
[Map](../map-class)\<K2, V2\> castFrom\<K, V, K2, V2\>(

1.  [Map](../map-class)\<K, V\> source

)
:::

Adapts `source` to be a `Map<K2, V2>`.

Any time the set would produce a key or value that is not a `K2` or
`V2`, the access will throw.

Any time `K2` key or `V2` value is attempted added into the adapted map,
the store will throw unless the key is also an instance of `K` and the
value is also an instance of `V`.

If all accessed entries of `source` are have `K2` keys and `V2` values
and if all entries added to the returned map have `K` keys and `V`\]
values, then the returned map can be used as a `Map<K2, V2>`.

Methods which accept `Object?` as argument, like
[containsKey](containskey), [remove](remove) and [operator
\[\]](operator_get), will pass the argument directly to the this map\'s
method without any checks.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Map<K2, V2> castFrom<K, V, K2, V2>(Map<K, V> source) =>
    CastMap<K, V, K2, V2>(source);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Map/castFrom.html>
:::
