[dart:collection](../../dart-collection/dart-collection-library){._links-link}

LinkedHashMap\<K, V\> constructor
=================================

::: {.section .multi-line-signature}
LinkedHashMap\<K, V\>(

1.  {[bool](../../dart-core/bool-class) equals(
    1.  K,
    2.  K

    )?,
2.  [int](../../dart-core/int-class) hashCode(
    1.  K

    )?,
3.  [bool](../../dart-core/bool-class) isValidKey(
    1.  dynamic

    )?}

)
:::

Creates an insertion-ordered hash-table based
[Map](../../dart-core/map-class).

If `equals` is provided, it is used to compare the keys in the table
with new keys. If `equals` is omitted, the key\'s own
[Object.==](../../dart-core/object/operator_equals) is used instead.

Similarly, if `hashCode` is provided, it is used to produce a hash value
for keys in order to place them in the hash table. If it is omitted, the
key\'s own [Object.hashCode](../../dart-core/object/hashcode) is used.

The used `equals` and `hashCode` method should always be consistent, so
that if `equals(a, b)` then `hashCode(a) == hashCode(b)`. The hash of an
object, or what it compares equal to, should not change while the object
is in the table. If it does change, the result is unpredictable.

If you supply one of `equals` or `hashCode`, you should generally also
supply the other.

Some `equals` or `hashCode` functions might not work for all objects. If
`isValidKey` is supplied, it\'s used to check a potential key which is
not necessarily an instance of `K`, like the arguments to [operator
\[\]](../../dart-core/map/operator_get),
[remove](../../dart-core/map/remove) and
[containsKey](../../dart-core/map/containskey), which are typed as
`Object?`. If `isValidKey` returns `false`, for an object, the `equals`
and `hashCode` functions are not called, and no key equal to that object
is assumed to be in the map. The `isValidKey` function defaults to just
testing if the object is an instance of `K`.

Example:

``` {.language-dart data-language="dart"}
LikedHashMap<int,int>(equals: (int a, int b) => (b - a) % 5 == 0,
                      hashCode: (int e) => e % 5)
```

This example map does not need an `isValidKey` function to be passed.
The default function accepts precisely `int` values, which can safely be
passed to both the `equals` and `hashCode` functions.

If neither `equals`, `hashCode`, nor `isValidKey` is provided, the
default `isValidKey` instead accepts all keys. The default equality and
hashcode operations are assumed to work on all objects.

Likewise, if `equals` is [identical](../../dart-core/identical),
`hashCode` is [identityHashCode](../../dart-core/identityhashcode) and
`isValidKey` is omitted, the resulting map is identity based, and the
`isValidKey` defaults to accepting all keys. Such a map can be created
directly using [LinkedHashMap.identity](linkedhashmap.identity).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory LinkedHashMap(
    {bool Function(K, K)? equals,
    int Function(K)? hashCode,
    bool Function(dynamic)? isValidKey});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/LinkedHashMap/LinkedHashMap.html>
:::
