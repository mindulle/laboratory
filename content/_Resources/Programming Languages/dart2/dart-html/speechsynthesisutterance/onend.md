[dart:html](../../dart-html/dart-html-library){._links-link}

onEnd property
==============

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[SpeechSynthesisEvent](../speechsynthesisevent-class)\>
onEnd
:::

Stream of `end` events handled by this
[SpeechSynthesisUtterance](../speechsynthesisutterance-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<SpeechSynthesisEvent> get onEnd => endEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SpeechSynthesisUtterance/onEnd.html>
:::
