[dart:async](../../dart-async/dart-async-library){._links-link}

close method
============

::: {.section .multi-line-signature}
[Future](../future-class) close()

::: {.features}
override
:::
:::

Closes the stream.

No further events can be added to a closed stream.

The returned future is the same future provided by [done](done). It is
completed when the stream listeners is done sending events, This happens
either when the done event has been sent, or when the subscriber on a
single-subscription stream is canceled.

A broadcast stream controller will send the done event even if listeners
are paused, so some broadcast events may not have been received yet when
the returned future completes.

If no one listens to a non-broadcast stream, or the listener pauses and
never resumes, the done event will not be sent and this future will
never complete.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future close();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamController/close.html>
:::
