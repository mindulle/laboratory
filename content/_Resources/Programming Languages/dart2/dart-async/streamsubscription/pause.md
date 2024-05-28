[dart:async](../../dart-async/dart-async-library){._links-link}

pause method
============

::: {.section .multi-line-signature}
void pause(

1.  \[[Future](../future-class)\<void\>? resumeSignal\]

)
:::

Requests that the stream pauses events until further notice.

While paused, the subscription will not fire any events. If it receives
events from its source, they will be buffered until the subscription is
resumed. For non-broadcast streams, the underlying source is usually
informed about the pause, so it can stop generating events until the
subscription is resumed.

To avoid buffering events on a broadcast stream, it is better to cancel
this subscription, and start to listen again when events are needed, if
the intermediate events are not important.

If `resumeSignal` is provided, the stream subscription will undo the
pause when the future completes, as if by a call to [resume](resume). If
the future completes with an error, the stream will still resume, but
the error will be considered unhandled and is passed to
[Zone.handleUncaughtError](../zone/handleuncaughterror).

A call to [resume](resume) will also undo a pause.

If the subscription is paused more than once, an equal number of resumes
must be performed to resume the stream. Calls to [resume](resume) and
the completion of a `resumeSignal` are interchangeable - the
[pause](pause) which was passed a `resumeSignal` may be ended by a call
to [resume](resume), and completing the `resumeSignal` may end a
different [pause](pause).

It is safe to [resume](resume) or complete a `resumeSignal` even when
the subscription is not paused, and the resume will have no effect.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void pause([Future<void>? resumeSignal]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamSubscription/pause.html>
:::
