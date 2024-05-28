[dart:html](../../dart-html/dart-html-library){._links-link}

onResume property
=================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[SpeechSynthesisEvent](../speechsynthesisevent-class)\>
onResume
:::

Stream of `resume` events handled by this
[SpeechSynthesisUtterance](../speechsynthesisutterance-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<SpeechSynthesisEvent> get onResume => resumeEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SpeechSynthesisUtterance/onResume.html>
:::
