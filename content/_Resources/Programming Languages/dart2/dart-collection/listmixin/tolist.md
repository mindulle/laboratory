[dart:collection](../../dart-collection/dart-collection-library){._links-link}

toList method
=============

::: {.section .multi-line-signature}
[List](../../dart-core/list-class)\<E\> toList(

1.  {[bool](../../dart-core/bool-class) growable = true}

)

::: {.features}
override
:::
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
  if (this.isEmpty) return List<E>.empty(growable: growable);
  var first = this[0];
  var result = List<E>.filled(this.length, first, growable: growable);
  for (int i = 1; i < this.length; i++) {
    result[i] = this[i];
  }
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListMixin/toList.html>
:::
