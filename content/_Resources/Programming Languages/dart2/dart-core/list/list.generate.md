[dart:core](../../dart-core/dart-core-library){._links-link}

List\<E\>.generate constructor
==============================

::: {.section .multi-line-signature}
List\<E\>.generate(

1.  [int](../int-class) length,
2.  E generator(
    1.  [int](../int-class) index

    ),
3.  {[bool](../bool-class) growable = true}

)
:::

Generates a list of values.

Creates a list with `length` positions and fills it with values created
by calling `generator` for each index in the range `0` .. `length - 1`
in increasing order.

``` {.language-dart data-language="dart"}
final growableList =
    List<int>.generate(3, (int index) => index * index, growable: true);
print(growableList); // [0, 1, 4]

final fixedLengthList =
    List<int>.generate(3, (int index) => index * index, growable: false);
print(fixedLengthList); // [0, 1, 4]
```

The created list is fixed-length if `growable` is set to false.

The `length` must be non-negative.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory List.generate(int length, E generator(int index),
    {bool growable = true});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/List.generate.html>
:::
