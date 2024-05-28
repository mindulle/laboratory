[dart:core](../../dart-core/dart-core-library){._links-link}

List\<E\> constructor
=====================

::: {.section .multi-line-signature}
<div>

1.  @[Deprecated](../deprecated-class)(\"Use a list literal, \[\], or
    the List.filled constructor instead\")

</div>

List\<E\>(

1.  \[[int](../int-class)? length\]

)
:::

Creates a list of the given length.

**NOTE**: This constructor cannot be used in null-safe code. Use
[List.filled](list.filled) to create a non-empty list. This requires a
fill value to initialize the list elements with. To create an empty
list, use `[]` for a growable list or `List.empty` for a fixed length
list (or where growability is determined at run-time).

The created list is fixed-length if `length` is provided.

``` {.language-dart data-language="dart"}
var fixedLengthList = List(3);
fixedLengthList.length;     // 3
fixedLengthList.length = 1; // Error
```

The list has length 0 and is growable if `length` is omitted.

``` {.language-dart data-language="dart"}
var growableList = List();
growableList.length; // 0;
growableList.length = 3;
```

To create a growable list with a given length, for a nullable element
type, just assign the length right after creation:

``` {.language-dart data-language="dart"}
List<SomeNullableType> growableList = []..length = 500;
```

For a non-nullable element type, an alternative is the following:

``` {.language-dart data-language="dart"}
List<int> growableList = List<int>.filled(500, 0, growable: true);
```

The `length` must not be negative or null, if it is provided.

If the element type is not nullable, `length` must not be greater than
zero.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Deprecated("Use a list literal, [], or the List.filled constructor instead")
external factory List([int? length]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/List.html>
:::
