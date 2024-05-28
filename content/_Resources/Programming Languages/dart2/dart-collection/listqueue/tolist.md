[dart:collection](../../dart-collection/dart-collection-library){._links-link}

toList method
=============

::: {.section .multi-line-signature}
[List](../../dart-core/list-class)\<E\> toList(

1.  {[bool](../../dart-core/bool-class) growable = true}

)
:::

Creates a [List](../../dart-core/list-class) containing the elements of
this [Iterable](../../dart-core/iterable-class).

The elements are in iteration order. The list is fixed-length if
`growable` is false.

Example:

``` {.language-dart data-language="dart"}
final planets = <int, String>{1: 'Mercury', 2: 'Venus', 3: 'Mars'};
final keysList = planets.keys.toList(growable: false); // [1, 2, 3]
final valuesList =
    planets.values.toList(growable: false); // [Mercury, Venus, Mars]
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<E> toList({bool growable = true}) {
  int mask = _table.length - 1;
  int length = (_tail - _head) & mask;
  if (length == 0) return List<E>.empty(growable: growable);

  var list = List<E>.filled(length, first, growable: growable);
  for (int i = 0; i < length; i++) {
    list[i] = _table[(_head + i) & mask] as E;
  }
  return list;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListQueue/toList.html>
:::
