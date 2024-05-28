[dart:html](../../dart-html/dart-html-library){._links-link}

speechStartEvent constant
=========================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const speechStartEvent
:::

Static factory designed to expose `speechstart` events to event handlers
that are not necessarily instances of
[SpeechRecognition](../speechrecognition-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> speechStartEvent =
    const EventStreamProvider<Event>('speechstart');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SpeechRecognition/speechStartEvent-constant.html>
:::
