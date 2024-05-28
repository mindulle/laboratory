[dart:async](../../dart-async/dart-async-library){._links-link}

cancel method
=============

::: {.section .multi-line-signature}
[Future](../future-class) cancel()
:::

Cancels the stream iterator (and the underlying stream subscription)
early.

The stream iterator is automatically canceled if the
[moveNext](movenext) future completes with either `false` or an error.

If you need to stop listening for values before the stream iterator is
automatically closed, you must call [cancel](cancel) to ensure that the
stream is properly closed.

If [moveNext](movenext) has been called when the iterator is canceled,
its returned future will complete with `false` as value, as will all
further calls to [moveNext](movenext).

Returns a future which completes when the cancellation is complete. This
can be an already completed future if the cancellation happens
synchronously.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future cancel();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamIterator/cancel.html>
:::
