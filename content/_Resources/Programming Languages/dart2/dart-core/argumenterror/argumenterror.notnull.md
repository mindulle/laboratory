[dart:core](../../dart-core/dart-core-library){._links-link}

ArgumentError.notNull constructor
=================================

::: {.section .multi-line-signature}
ArgumentError.notNull(

1.  \[[String](../string-class)? name\]

)
:::

Creates an argument error for a `null` argument that must not be `null`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ArgumentError.notNull([this.name])
    : _hasValue = false,
      message = "Must not be null",
      invalidValue = null;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/ArgumentError/ArgumentError.notNull.html>
:::
