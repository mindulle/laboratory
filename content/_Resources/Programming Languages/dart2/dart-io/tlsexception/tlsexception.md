[dart:io](../../dart-io/dart-io-library){._links-link}

TlsException constructor
========================

::: {.section .multi-line-signature}
const TlsException(

1.  \[[String](../../dart-core/string-class) message = \"\",
2.  [OSError](../oserror-class)? osError\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma("vm:entry-point")
const TlsException([String message = "", OSError? osError])
    : this._("TlsException", message, osError);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/TlsException/TlsException.html>
:::
