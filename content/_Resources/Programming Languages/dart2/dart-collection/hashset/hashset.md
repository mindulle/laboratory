[dart:collection](../../dart-collection/dart-collection-library){._links-link}

HashSet\<E\> constructor
========================

::: {.section .multi-line-signature}
HashSet\<E\>(

1.  {[bool](../../dart-core/bool-class) equals(
    1.  E,
    2.  E

    )?,
2.  [int](../../dart-core/int-class) hashCode(
    1.  E

    )?,
3.  [bool](../../dart-core/bool-class) isValidKey(
    1.  dynamic

    )?}

)
:::

Create a hash set using the provided `equals` as equality.

The provided `equals` must define a stable equivalence relation, and
`hashCode` must be consistent with `equals`.

If `equals` or `hashCode` are omitted, the set uses the elements\'
intrinsic [Object.==](../../dart-core/object/operator_equals) and
[Object.hashCode](../../dart-core/object/hashcode).

If you supply one of `equals` and `hashCode`, you should generally also
supply the other.

Some `equals` or `hashCode` functions might not work for all objects. If
`isValidKey` is supplied, it\'s used to check a potential element which
is not necessarily an instance of `E`, like the argument to
[contains](../../dart-core/set/contains) which is typed as `Object?`. If
`isValidKey` returns `false`, for an object, the `equals` and `hashCode`
functions are not called, and no key equal to that object is assumed to
be in the map. The `isValidKey` function defaults to just testing if the
object is an instance of `E`, which means that:

``` {.language-dart data-language="dart"}
HashSet<int>(equals: (int e1, int e2) => (e1 - e2) % 5 == 0,
             hashCode: (int e) => e % 5)
```

does not need an `isValidKey` argument because it defaults to only
accepting `int` values which are accepted by both `equals` and
`hashCode`.

If neither `equals`, `hashCode`, nor `isValidKey` is provided, the
default `isValidKey` instead accepts all values. The default equality
and hashcode operations are assumed to work on all objects.

Likewise, if `equals` is [identical](../../dart-core/identical),
`hashCode` is [identityHashCode](../../dart-core/identityhashcode) and
`isValidKey` is omitted, the resulting set is identity based, and the
`isValidKey` defaults to accepting all keys. Such a map can be created
directly using [HashSet.identity](hashset.identity).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory HashSet(
    {bool Function(E, E)? equals,
    int Function(E)? hashCode,
    bool Function(dynamic)? isValidKey});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/HashSet/HashSet.html>
:::
