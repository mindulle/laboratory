[dart:web\_audio](../../dart-web_audio/dart-web_audio-library){._links-link}

audioProcessEvent constant
==========================

::: {.section .multi-line-signature}
[EventStreamProvider](../../dart-html/eventstreamprovider-class)\<[AudioProcessingEvent](../audioprocessingevent-class)\>
const audioProcessEvent
:::

Static factory designed to expose `audioprocess` events to event
handlers that are not necessarily instances of
[ScriptProcessorNode](../scriptprocessornode-class).

See [EventStreamProvider](../../dart-html/eventstreamprovider-class) for
usage information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<AudioProcessingEvent> audioProcessEvent =
    const EventStreamProvider<AudioProcessingEvent>('audioprocess');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_audio/ScriptProcessorNode/audioProcessEvent-constant.html>
:::
