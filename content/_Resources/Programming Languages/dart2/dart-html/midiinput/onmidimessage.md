[dart:html](../../dart-html/dart-html-library){._links-link}

onMidiMessage property
======================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[MidiMessageEvent](../midimessageevent-class)\>
onMidiMessage
:::

Stream of `midimessage` events handled by this
[MidiInput](../midiinput-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<MidiMessageEvent> get onMidiMessage =>
    midiMessageEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MidiInput/onMidiMessage.html>
:::
