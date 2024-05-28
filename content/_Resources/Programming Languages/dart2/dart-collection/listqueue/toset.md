[dart:collection](../../dart-collection/dart-collection-library){._links-link}

toSet method
============

::: {.section .multi-line-signature}
[Set](../../dart-core/set-class)\<E\> toSet()

::: {.features}
inherited
:::
:::

Creates a [Set](../../dart-core/set-class) containing the same elements
as this iterable.

The set may contain fewer elements than the iterable, if the iterable
contains an element more than once, or it contains one or more elements
that are equal. The order of the elements in the set is not guaranteed
to be the same as for the iterable.

Example:

``` {.language-dart data-language="dart"}
final planets = <int, String>{1: 'Mercury', 2: 'Venus', 3: 'Mars'};
final valueSet = planets.values.toSet(); // {Mercury, Venus, Mars}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Set<E> toSet() {
  Set<E> result = Set<E>();
  for (int i = 0; i < length; i++) {
    result.add(elementAt(i));
  }
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListQueue/toSet.html>
:::
