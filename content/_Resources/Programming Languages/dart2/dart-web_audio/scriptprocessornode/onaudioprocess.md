[dart:web\_audio](../../dart-web_audio/dart-web_audio-library){._links-link}

onAudioProcess property
=======================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[AudioProcessingEvent](../audioprocessingevent-class)\>
onAudioProcess
:::

Get a Stream that fires events when AudioProcessingEvents occur. This
particular stream is special in that it only allows one listener to a
given stream. Converting the returned
[Stream.asBroadcastStream](../../dart-async/stream/asbroadcaststream)
will likely ruin the soft-real-time properties which which these events
are fired and can be processed.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<AudioProcessingEvent> get onAudioProcess =>
      audioProcessEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_audio/ScriptProcessorNode/onAudioProcess.html>
:::
