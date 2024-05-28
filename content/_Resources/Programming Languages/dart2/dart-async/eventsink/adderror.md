[dart:async](../../dart-async/dart-async-library){._links-link}

addError method
===============

::: {.section .multi-line-signature}
void addError(

1.  [Object](../../dart-core/object-class) error,
2.  \[[StackTrace](../../dart-core/stacktrace-class)? stackTrace\]

)
:::

Adds an `error` to the sink.

Must not be called on a closed sink.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addError(Object error, [StackTrace? stackTrace]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/EventSink/addError.html>
:::
