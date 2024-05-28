[dart:io](../dart-io/dart-io-library){._links-link}

stderr top-level property
=========================

::: {#getter .section .multi-line-signature}
[Stdout](stdout-class) stderr
:::

The standard output stream of errors written by this program.

The `addError` API is inherited from `StreamSink` and calling it will
result in an unhandled asynchronous error unless there is an error
handler on `done`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stdout get stderr {
  return IOOverrides.current?.stderr ?? _stderr;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/stderr.html>
:::
