[dart:html](../../dart-html/dart-html-library){._links-link}

onWheel property
================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[WheelEvent](../wheelevent-class)\>
onWheel

::: {.features}
override
:::
:::

Stream of `wheel` events handled by this [Window](../window-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<WheelEvent> get onWheel => Element.wheelEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/onWheel.html>
:::
