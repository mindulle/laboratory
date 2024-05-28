[dart:core](../../dart-core/dart-core-library){._links-link}

contains method
===============

::: {.section .multi-line-signature}
[bool](../bool-class) contains(

1.  [Object](../object-class)? element

)
:::

Whether the collection contains an element equal to `element`.

This operation will check each element in order for being equal to
`element`, unless it has a more efficient way to find an element equal
to `element`.

The equality used to determine whether `element` is equal to an element
of the iterable defaults to the [Object.==](../object/operator_equals)
of the element.

Some types of iterable may have a different equality used for its
elements. For example, a [Set](../set-class) may have a custom equality
(see [Set.identity](../set/set.identity)) that its `contains` uses.
Likewise the `Iterable` returned by a [Map.keys](../map/keys) call
should use the same equality that the `Map` uses for keys.

Example:

``` {.language-dart data-language="dart"}
final gasPlanets = <int, String>{1: 'Jupiter', 2: 'Saturn'};
final containsOne = gasPlanets.keys.contains(1); // true
final containsFive = gasPlanets.keys.contains(5); // false
final containsJupiter = gasPlanets.values.contains('Jupiter'); // true
final containsMercury = gasPlanets.values.contains('Mercury'); // false
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool contains(Object? element) {
  for (E e in this) {
    if (e == element) return true;
  }
  return false;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Iterable/contains.html>
:::
