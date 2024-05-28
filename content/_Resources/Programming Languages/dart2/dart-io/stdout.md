[dart:io](../dart-io/dart-io-library){._links-link}

stdout top-level property
=========================

::: {#getter .section .multi-line-signature}
[Stdout](stdout-class) stdout
:::

The standard output stream of data written by this program.

The `addError` API is inherited from `StreamSink` and calling it will
result in an unhandled asynchronous error unless there is an error
handler on `done`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stdout get stdout {
  return IOOverrides.current?.stdout ?? _stdout;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/stdout.html>
:::
