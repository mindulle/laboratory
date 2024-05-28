[dart:core](../../dart-core/dart-core-library){._links-link}

ArgumentError constructor
=========================

::: {.section .multi-line-signature}
ArgumentError(

1.  \[dynamic message,
2.  \@Since(\"2.14\") [String](../string-class)? name\]

)
:::

Creates an error with [message](message) describing the problem with an
argument.

Existing code may be using `message` to hold the invalid value. If the
`message` is not a [String](../string-class), it is assumed to be a
value instead of a message.

If [name](name) is provided, it should be the name of the parameter
which was invalid.

Consider using [ArgumentError.value](argumenterror.value) instead to
retain and document the invalid value as well.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma("vm:entry-point")
ArgumentError([this.message, @Since("2.14") this.name])
    : invalidValue = null,
      _hasValue = false;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/ArgumentError/ArgumentError.html>
:::
