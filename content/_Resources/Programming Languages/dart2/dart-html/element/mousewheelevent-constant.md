[dart:html](../../dart-html/dart-html-library){._links-link}

mouseWheelEvent constant
========================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[WheelEvent](../wheelevent-class)\>
const mouseWheelEvent
:::

Static factory designed to expose `mousewheel` events to event handlers
that are not necessarily instances of [Element](../element-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<WheelEvent> mouseWheelEvent =
    const _CustomEventStreamProvider<WheelEvent>(
        Element._determineMouseWheelEventType);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/mouseWheelEvent-constant.html>
:::
