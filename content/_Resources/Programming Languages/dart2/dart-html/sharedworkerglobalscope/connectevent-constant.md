[dart:html](../../dart-html/dart-html-library){._links-link}

connectEvent constant
=====================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const connectEvent
:::

Static factory designed to expose `connect` events to event handlers
that are not necessarily instances of
[SharedWorkerGlobalScope](../sharedworkerglobalscope-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> connectEvent =
    const EventStreamProvider<Event>('connect');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SharedWorkerGlobalScope/connectEvent-constant.html>
:::
