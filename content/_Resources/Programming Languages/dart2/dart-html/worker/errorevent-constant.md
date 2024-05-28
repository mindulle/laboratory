[dart:html](../../dart-html/dart-html-library){._links-link}

errorEvent constant
===================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const errorEvent
:::

Static factory designed to expose `error` events to event handlers that
are not necessarily instances of [Worker](../worker-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> errorEvent =
    const EventStreamProvider<Event>('error');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Worker/errorEvent-constant.html>
:::
