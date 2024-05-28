[dart:html](../../dart-html/dart-html-library){._links-link}

mouseUpEvent constant
=====================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[MouseEvent](../mouseevent-class)\>
const mouseUpEvent
:::

Static factory designed to expose `mouseup` events to event handlers
that are not necessarily instances of [Element](../element-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<MouseEvent> mouseUpEvent =
    const EventStreamProvider<MouseEvent>('mouseup');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/mouseUpEvent-constant.html>
:::
