[dart:core](../../dart-core/dart-core-library){._links-link}

toSet method
============

::: {.section .multi-line-signature}
[Set](../set-class)\<E\> toSet()
:::

Creates a [Set](../set-class) containing the same elements as this
iterable.

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
Set<E> toSet() => Set<E>.of(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Iterable/toSet.html>
:::
