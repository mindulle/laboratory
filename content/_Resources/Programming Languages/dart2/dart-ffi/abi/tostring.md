[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

toString method
===============

::: {.section .multi-line-signature}
<div>

1.  @[override](../../dart-core/override-constant)

</div>

[String](../../dart-core/string-class) toString()

::: {.features}
override
:::
:::

A string representation of this ABI.

The string is equal to the \'on\' part from `Platform.version` and
`dart --version`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@override
String toString() => '${_os.name}_${_architecture.name}';
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Abi/toString.html>
:::
