[dart:core](../../dart-core/dart-core-library){._links-link}

List\<E\>.unmodifiable constructor
==================================

::: {.section .multi-line-signature}
List\<E\>.unmodifiable(

1.  [Iterable](../iterable-class) elements

)
:::

Creates an unmodifiable list containing all `elements`.

The [Iterator](../iterator-class) of `elements` provides the order of
the elements.

An unmodifiable list cannot have its length or elements changed. If the
elements are themselves immutable, then the resulting list is also
immutable.

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3];
final unmodifiableList = List.unmodifiable(numbers); // [1, 2, 3]
unmodifiableList[1] = 87; // Throws.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory List.unmodifiable(Iterable elements);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/List.unmodifiable.html>
:::
