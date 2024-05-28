[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

kill method
===========

::: {.section .multi-line-signature}
void kill(

1.  {[int](../../dart-core/int-class) priority = beforeNextEvent}

)
:::

Requests the isolate to shut down.

The isolate is requested to terminate itself. The `priority` argument
specifies when this must happen.

The `priority`, when provided, must be one of
[immediate](immediate-constant) or
[beforeNextEvent](beforenextevent-constant) (the default). The shutdown
is performed at different times depending on the priority:

-   `immediate`: The isolate shuts down as soon as possible. Control
    messages are handled in order, so all previously sent control events
    from this isolate will all have been processed. The shutdown should
    happen no later than if sent with `beforeNextEvent`. It may happen
    earlier if the system has a way to shut down cleanly at an earlier
    time, even during the execution of another event.
-   `beforeNextEvent`: The shutdown is scheduled for the next time
    control returns to the event loop of the receiving isolate, after
    the current event, and any already scheduled control events, are
    completed.

If [terminateCapability](terminatecapability) is `null`, or it\'s not
the terminate capability of the isolate identified by
[controlPort](controlport), the kill request is ignored by the receiving
isolate.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external void kill({int priority = beforeNextEvent});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Isolate/kill.html>
:::
