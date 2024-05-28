[dart:collection](../../dart-collection/dart-collection-library){._links-link}

SplayTreeSet\<E\> constructor
=============================

::: {.section .multi-line-signature}
SplayTreeSet\<E\>(

1.  \[[int](../../dart-core/int-class) compare(
    1.  E key1,
    2.  E key2

    )?,
2.  [bool](../../dart-core/bool-class) isValidKey(
    1.  dynamic potentialKey

    )?\]

)
:::

Create a new [SplayTreeSet](../splaytreeset-class) with the given
compare function.

If the `compare` function is omitted, it defaults to
[Comparable.compare](../../dart-core/comparable/compare), and the
elements must be comparable.

A provided `compare` function may not work on all objects. It may not
even work on all `E` instances.

For operations that add elements to the set, the user is supposed to not
pass in objects that don\'t work with the compare function.

The methods [contains](contains), [remove](remove), [lookup](lookup),
[removeAll](removeall) or [retainAll](retainall) are typed to accept any
object(s), and the `isValidKey` test can used to filter those objects
before handing them to the `compare` function.

If `isValidKey` is provided, only values satisfying `isValidKey(other)`
are compared using the `compare` method in the methods mentioned above.
If the `isValidKey` function returns false for an object, it is assumed
to not be in the set.

If omitted, the `isValidKey` function defaults to checking against the
type parameter: `other is E`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
SplayTreeSet(
    [int Function(E key1, E key2)? compare,
    bool Function(dynamic potentialKey)? isValidKey])
    : _compare = compare ?? _defaultCompare<E>(),
      _validKey = isValidKey ?? ((dynamic v) => v is E);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeSet/SplayTreeSet.html>
:::
