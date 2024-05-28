[dart:html](../../dart-html/dart-html-library){._links-link}

resumeEvent constant
====================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[SpeechSynthesisEvent](../speechsynthesisevent-class)\>
const resumeEvent
:::

Static factory designed to expose `resume` events to event handlers that
are not necessarily instances of
[SpeechSynthesisUtterance](../speechsynthesisutterance-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<SpeechSynthesisEvent> resumeEvent =
    const EventStreamProvider<SpeechSynthesisEvent>('resume');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SpeechSynthesisUtterance/resumeEvent-constant.html>
:::
