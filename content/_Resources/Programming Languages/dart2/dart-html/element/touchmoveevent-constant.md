[dart:html](../../dart-html/dart-html-library){._links-link}

touchMoveEvent constant
=======================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[TouchEvent](../touchevent-class)\>
const touchMoveEvent
:::

Static factory designed to expose `touchmove` events to event handlers
that are not necessarily instances of [Element](../element-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<TouchEvent> touchMoveEvent =
    const EventStreamProvider<TouchEvent>('touchmove');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/touchMoveEvent-constant.html>
:::
