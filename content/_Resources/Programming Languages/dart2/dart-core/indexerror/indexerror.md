[dart:core](../../dart-core/dart-core-library){._links-link}

IndexError constructor
======================

::: {.section .multi-line-signature}
IndexError(

1.  [int](../int-class) invalidValue,
2.  dynamic indexable,
3.  \[[String](../string-class)? name,
4.  [String](../string-class)? message,
5.  [int](../int-class)? length\]

)
:::

Creates a new [IndexError](../indexerror-class) stating that
`invalidValue` is not a valid index into `indexable`.

The `length` is the length of `indexable` at the time of the error. If
`length` is omitted, it defaults to `indexable.length`.

The message is used as part of the string representation of the error.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
IndexError(int invalidValue, dynamic indexable,
    [String? name, String? message, int? length])
    : this.indexable = indexable,
      this.length = length ?? indexable.length,
      super.value(invalidValue, name, message ?? "Index out of range");
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/IndexError/IndexError.html>
:::
