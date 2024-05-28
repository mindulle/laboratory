[dart:html](../../dart-html/dart-html-library){._links-link}

onMute property
===============

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[Event](../event-class)\>
onMute
:::

Stream of `mute` events handled by this
[MediaStreamTrack](../mediastreamtrack-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<Event> get onMute => muteEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaStreamTrack/onMute.html>
:::
