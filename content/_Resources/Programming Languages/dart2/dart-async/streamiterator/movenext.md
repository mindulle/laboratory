[dart:async](../../dart-async/dart-async-library){._links-link}

moveNext method
===============

::: {.section .multi-line-signature}
[Future](../future-class)\<[bool](../../dart-core/bool-class)\>
moveNext()
:::

Wait for the next stream value to be available.

Returns a future which will complete with either `true` or `false`.
Completing with `true` means that another event has been received and
can be read as [current](current). Completing with `false` means that
the stream iteration is done and no further events will ever be
available. The future may complete with an error, if the stream produces
an error, which also ends iteration.

The function must not be called again until the future returned by a
previous call is completed.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<bool> moveNext();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamIterator/moveNext.html>
:::
