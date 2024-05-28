[dart:core](../../dart-core/dart-core-library){._links-link}

RangeError.index constructor
============================

::: {.section .multi-line-signature}
RangeError.index(

1.  [int](../int-class) index,
2.  dynamic indexable,
3.  \[[String](../string-class)? name,
4.  [String](../string-class)? message,
5.  [int](../int-class)? length\]

)
:::

Creates a new [RangeError](../rangeerror-class) stating that `index` is
not a valid index into `indexable`.

An optional `name` can specify the argument name that has the invalid
value, and the `message` can override the default error description.

The `length` is the length of `indexable` at the time of the error. If
`length` is omitted, it defaults to `indexable.length`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory RangeError.index(int index, dynamic indexable,
    [String? name, String? message, int? length]) = IndexError;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RangeError/RangeError.index.html>
:::
