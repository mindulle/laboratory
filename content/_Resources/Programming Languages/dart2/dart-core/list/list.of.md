[dart:core](../../dart-core/dart-core-library){._links-link}

List\<E\>.of constructor
========================

::: {.section .multi-line-signature}
List\<E\>.of(

1.  [Iterable](../iterable-class)\<E\> elements,
2.  {[bool](../bool-class) growable = true}

)
:::

Creates a list from `elements`.

The [Iterator](../iterator-class) of `elements` provides the order of
the elements.

This constructor creates a growable list when `growable` is true;
otherwise, it returns a fixed-length list.

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3];
final listOf = List<num>.of(numbers);
print(listOf); // [1, 2, 3]
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory List.of(Iterable<E> elements, {bool growable = true});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/List.of.html>
:::
