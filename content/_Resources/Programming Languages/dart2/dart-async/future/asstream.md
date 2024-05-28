[dart:async](../../dart-async/dart-async-library){._links-link}

asStream method
===============

::: {.section .multi-line-signature}
[Stream](../stream-class)\<T\> asStream()
:::

Creates a [Stream](../stream-class) containing the result of this
future.

The stream will produce single data or error event containing the
completion result of this future, and then it will close with a done
event.

If the future never completes, the stream will not produce any events.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<T> asStream();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Future/asStream.html>
:::
