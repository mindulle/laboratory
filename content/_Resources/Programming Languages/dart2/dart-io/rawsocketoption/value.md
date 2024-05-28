[dart:io](../../dart-io/dart-io-library){._links-link}

value property
==============

::: {.section .multi-line-signature}
[Uint8List](../../dart-typed_data/uint8list-class) value

::: {.features}
final
:::
:::

The raw data to set, or the array to write the current option value
into.

This list must be the correct length for the expected option. For most
options that take [int](../../dart-core/int-class) or
[bool](../../dart-core/bool-class) values, the length should be 4. For
options that expect a struct (such as an in\_addr\_t), the length should
be the correct length for that struct.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final Uint8List value;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSocketOption/value.html>
:::
