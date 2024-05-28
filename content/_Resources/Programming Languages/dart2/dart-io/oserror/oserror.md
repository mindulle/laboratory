[dart:io](../../dart-io/dart-io-library){._links-link}

OSError constructor
===================

::: {.section .multi-line-signature}
const OSError(

1.  \[[String](../../dart-core/string-class) message = \"\",
2.  [int](../../dart-core/int-class) errorCode = noErrorCode\]

)
:::

Creates an OSError object from a message and an errorCode.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma("vm:entry-point")
const OSError([this.message = "", this.errorCode = noErrorCode]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/OSError/OSError.html>
:::
