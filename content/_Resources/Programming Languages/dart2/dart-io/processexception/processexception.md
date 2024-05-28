[dart:io](../../dart-io/dart-io-library){._links-link}

ProcessException constructor
============================

::: {.section .multi-line-signature}
const ProcessException(

1.  [String](../../dart-core/string-class) executable,
2.  [List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>
    arguments,
3.  \[[String](../../dart-core/string-class) message = \"\",
4.  [int](../../dart-core/int-class) errorCode = 0\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const ProcessException(this.executable, this.arguments,
    [this.message = "", this.errorCode = 0]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ProcessException/ProcessException.html>
:::
