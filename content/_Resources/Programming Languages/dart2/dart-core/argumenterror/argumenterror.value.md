[dart:core](../../dart-core/dart-core-library){._links-link}

ArgumentError.value constructor
===============================

::: {.section .multi-line-signature}
ArgumentError.value(

1.  dynamic value,
2.  \[[String](../string-class)? name,
3.  dynamic message\]

)
:::

Creates error containing the invalid `value`.

A message is built by suffixing the [message](message) argument with the
[name](name) argument (if provided) and the value. Example:

``` {.language-plaintext data-language="dart"}
Invalid argument (foo): null
```

The `name` should match the argument name of the function, but if the
function is a method implementing an interface, and its argument names
differ from the interface, it might be more useful to use the interface
method\'s argument name (or just rename arguments to match).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma("vm:entry-point")
ArgumentError.value(value, [this.name, this.message])
    : invalidValue = value,
      _hasValue = true;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/ArgumentError/ArgumentError.value.html>
:::
