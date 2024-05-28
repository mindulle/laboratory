[dart:io](../../dart-io/dart-io-library){._links-link}

nonBlocking property
====================

::: {#getter .section .multi-line-signature}
[IOSink](../iosink-class) nonBlocking
:::

A non-blocking `IOSink` for the same output.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
IOSink get nonBlocking {
  return _nonBlocking ??= new IOSink(new _FileStreamConsumer.fromStdio(_fd));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Stdout/nonBlocking.html>
:::
