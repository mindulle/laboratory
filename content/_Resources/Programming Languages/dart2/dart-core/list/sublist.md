[dart:core](../../dart-core/dart-core-library){._links-link}

sublist method
==============

::: {.section .multi-line-signature}
[List](../list-class)\<E\> sublist(

1.  [int](../int-class) start,
2.  \[[int](../int-class)? end\]

)
:::

Returns a new list containing the elements between `start` and `end`.

The new list is a `List<E>` containing the elements of this list at
positions greater than or equal to `start` and less than `end` in the
same order as they occur in this list.

``` {.language-dart data-language="dart"}
final colors = <String>['red', 'green', 'blue', 'orange', 'pink'];
print(colors.sublist(1, 3)); // [green, blue]
```

If `end` is omitted, it defaults to the [length](length) of this list.

``` {.language-dart data-language="dart"}
final colors = <String>['red', 'green', 'blue', 'orange', 'pink'];
print(colors.sublist(3)); // [orange, pink]
```

The `start` and `end` positions must satisfy the relations 0 ≤ `start` ≤
`end` ≤ [length](length). If `end` is equal to `start`, then the
returned list is empty.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<E> sublist(int start, [int? end]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/sublist.html>
:::
