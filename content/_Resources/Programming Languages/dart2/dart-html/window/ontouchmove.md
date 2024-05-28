[dart:html](../../dart-html/dart-html-library){._links-link}

onTouchMove property
====================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[TouchEvent](../touchevent-class)\>
onTouchMove

::: {.features}
override
:::
:::

Stream of `touchmove` events handled by this [Window](../window-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<TouchEvent> get onTouchMove => Element.touchMoveEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/onTouchMove.html>
:::
