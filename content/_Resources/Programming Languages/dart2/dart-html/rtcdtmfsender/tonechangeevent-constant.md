[dart:html](../../dart-html/dart-html-library){._links-link}

toneChangeEvent constant
========================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[RtcDtmfToneChangeEvent](../rtcdtmftonechangeevent-class)\>
const toneChangeEvent
:::

Static factory designed to expose `tonechange` events to event handlers
that are not necessarily instances of
[RtcDtmfSender](../rtcdtmfsender-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<RtcDtmfToneChangeEvent> toneChangeEvent =
    const EventStreamProvider<RtcDtmfToneChangeEvent>('tonechange');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcDtmfSender/toneChangeEvent-constant.html>
:::
