[dart:io](../../dart-io/dart-io-library){._links-link}

close method
============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) close()

::: {.features}
override
:::
:::

Close the target consumer.

NOTE: Writes to the [IOSink](../iosink-class) may be buffered, and may
not be flushed by a call to `close()`. To flush all buffered writes,
call `flush()` before calling `close()`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future close();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Socket/close.html>
:::
