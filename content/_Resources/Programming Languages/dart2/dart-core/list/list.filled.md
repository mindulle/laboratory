[dart:core](../../dart-core/dart-core-library){._links-link}

List\<E\>.filled constructor
============================

::: {.section .multi-line-signature}
List\<E\>.filled(

1.  [int](../int-class) length,
2.  E fill,
3.  {[bool](../bool-class) growable = false}

)
:::

Creates a list of the given length with `fill` at each position.

The `length` must be a non-negative integer.

Example:

``` {.language-dart data-language="dart"}
final zeroList = List<int>.filled(3, 0, growable: true); // [0, 0, 0]
```

The created list is fixed-length if `growable` is false (the default)
and growable if `growable` is true. If the list is growable, increasing
its `length` will *not* initialize new entries with `fill`. After being
created and filled, the list is no different from any other growable or
fixed-length list created using `[]` or other [List](../list-class)
constructors.

All elements of the created list share the same `fill` value.

``` {.language-dart data-language="dart"}
final shared = List.filled(3, []);
shared[0].add(499);
print(shared);  // [[499], [499], [499]]
```

You can use [List.generate](list.generate) to create a list with a fixed
length and a new object at each position.

``` {.language-dart data-language="dart"}
final unique = List.generate(3, (_) => []);
unique[0].add(499);
print(unique); // [[499], [], []]
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory List.filled(int length, E fill, {bool growable = false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/List.filled.html>
:::
