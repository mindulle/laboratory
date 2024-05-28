[dart:html](../../dart-html/dart-html-library){._links-link}

onToneChange property
=====================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[RtcDtmfToneChangeEvent](../rtcdtmftonechangeevent-class)\>
onToneChange
:::

Stream of `tonechange` events handled by this
[RtcDtmfSender](../rtcdtmfsender-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<RtcDtmfToneChangeEvent> get onToneChange =>
    toneChangeEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcDtmfSender/onToneChange.html>
:::
