[dart:html](../../dart-html/dart-html-library){._links-link}

midiMessageEvent constant
=========================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[MidiMessageEvent](../midimessageevent-class)\>
const midiMessageEvent
:::

Static factory designed to expose `midimessage` events to event handlers
that are not necessarily instances of [MidiInput](../midiinput-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<MidiMessageEvent> midiMessageEvent =
    const EventStreamProvider<MidiMessageEvent>('midimessage');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MidiInput/midiMessageEvent-constant.html>
:::
