[dart:io](../../dart-io/dart-io-library){._links-link}

flush method
============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) flush()

::: {.features}
inherited
:::
:::

Returns a [Future](../../dart-async/future-class) that completes once
all buffered data is accepted by the underlying
[StreamConsumer](../../dart-async/streamconsumer-class).

This method must not be called while an [addStream](addstream) is
incomplete.

NOTE: This is not necessarily the same as the data being flushed by the
operating system.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future flush() => _sink.flush();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Stdout/flush.html>
:::
