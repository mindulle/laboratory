[dart:async](../../dart-async/dart-async-library){._links-link}

done property
=============

::: {#getter .section .multi-line-signature}
[Future](../future-class) done

::: {.features}
override
:::
:::

A future which is completed when the stream controller is done sending
events.

This happens either when the done event has been sent, or if the
subscriber on a single-subscription stream is canceled.

A broadcast stream controller will send the done event even if listeners
are paused, so some broadcast events may not have been received yet when
the returned future completes.

If there is no listener on a non-broadcast stream, or the listener
pauses and never resumes, the done event will not be sent and this
future will never complete.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future get done;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamController/done.html>
:::
