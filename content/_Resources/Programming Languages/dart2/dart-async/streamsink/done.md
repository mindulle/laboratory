[dart:async](../../dart-async/dart-async-library){._links-link}

done property
=============

::: {#getter .section .multi-line-signature}
[Future](../future-class) done
:::

Return a future which is completed when the
[StreamSink](../streamsink-class) is finished.

If the `StreamSink` fails with an error, perhaps in response to adding
events using [add](../eventsink/add), [addError](../eventsink/adderror)
or [close](close), the [done](done) future will complete with that
error.

Otherwise, the returned future will complete when either:

-   all events have been processed and the sink has been closed, or
-   the sink has otherwise been stopped from handling more events (for
    example by canceling a stream subscription).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future get done;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamSink/done.html>
:::
