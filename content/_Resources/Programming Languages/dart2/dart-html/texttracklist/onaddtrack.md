[dart:html](../../dart-html/dart-html-library){._links-link}

onAddTrack property
===================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[TrackEvent](../trackevent-class)\>
onAddTrack
:::

Stream of `addtrack` events handled by this
[TextTrackList](../texttracklist-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<TrackEvent> get onAddTrack => addTrackEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/TextTrackList/onAddTrack.html>
:::
