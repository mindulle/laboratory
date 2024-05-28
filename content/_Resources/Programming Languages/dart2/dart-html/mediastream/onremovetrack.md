[dart:html](../../dart-html/dart-html-library){._links-link}

onRemoveTrack property
======================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[Event](../event-class)\>
onRemoveTrack
:::

Stream of `removetrack` events handled by this
[MediaStream](../mediastream-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<Event> get onRemoveTrack => removeTrackEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaStream/onRemoveTrack.html>
:::
