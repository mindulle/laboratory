[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

sublist method
==============

::: {.section .multi-line-signature}
[Float64List](../float64list-class) sublist(

1.  [int](../../dart-core/int-class) start,
2.  \[[int](../../dart-core/int-class)? end\]

)

::: {.features}
override
:::
:::

Returns a new list containing the elements between `start` and `end`.

The new list is a `Float64List` containing the elements of this list at
positions greater than or equal to `start` and less than `end` in the
same order as they occur in this list.

``` {.language-dart data-language="dart"}
var numbers = Float64List.fromList([0, 1, 2, 3, 4]);
print(numbers.sublist(1, 3)); // [1, 2]
print(numbers.sublist(1, 3).runtimeType); // Float64List
```

If `end` is omitted, it defaults to the
[length](../../dart-core/list/length) of this list.

``` {.language-dart data-language="dart"}
print(numbers.sublist(1)); // [1, 2, 3, 4]
```

The `start` and `end` positions must satisfy the relations 0 ≤ `start` ≤
`end` ≤ `this.length` If `end` is equal to `start`, then the returned
list is empty.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Float64List sublist(int start, [int? end]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/Float64List/sublist.html>
:::
