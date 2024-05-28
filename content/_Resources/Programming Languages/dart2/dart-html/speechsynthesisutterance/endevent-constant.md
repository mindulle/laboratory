[dart:html](../../dart-html/dart-html-library){._links-link}

endEvent constant
=================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[SpeechSynthesisEvent](../speechsynthesisevent-class)\>
const endEvent
:::

Static factory designed to expose `end` events to event handlers that
are not necessarily instances of
[SpeechSynthesisUtterance](../speechsynthesisutterance-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<SpeechSynthesisEvent> endEvent =
    const EventStreamProvider<SpeechSynthesisEvent>('end');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SpeechSynthesisUtterance/endEvent-constant.html>
:::
