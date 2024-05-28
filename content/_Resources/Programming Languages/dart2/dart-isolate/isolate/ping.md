[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

ping method
===========

::: {.section .multi-line-signature}
void ping(

1.  [SendPort](../sendport-class) responsePort,
2.  {[Object](../../dart-core/object-class)? response,
3.  [int](../../dart-core/int-class) priority = immediate}

)
:::

Requests that the isolate send `response` on the `responsePort`.

The `response` object must follow the same restrictions as enforced by
[SendPort.send](../sendport/send). It is recommended to only use simple
values that can be sent to all isolates, like `null`, booleans, numbers
or strings.

If the isolate is alive, it will eventually send `response` (defaulting
to `null`) on the response port.

The `priority` must be one of [immediate](immediate-constant) or
[beforeNextEvent](beforenextevent-constant). The response is sent at
different times depending on the ping type:

-   `immediate`: The isolate responds as soon as it receives the control
    message. This is after any previous control message from the same
    isolate has been received and processed, but may be during execution
    of another event.
-   `beforeNextEvent`: The response is scheduled for the next time
    control returns to the event loop of the receiving isolate, after
    the current event, and any already scheduled control events, are
    completed.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external void ping(SendPort responsePort,
    {Object? response, int priority = immediate});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Isolate/ping.html>
:::
