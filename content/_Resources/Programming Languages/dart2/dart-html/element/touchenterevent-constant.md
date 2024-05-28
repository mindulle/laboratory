[dart:html](../../dart-html/dart-html-library){._links-link}

touchEnterEvent constant
========================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[TouchEvent](../touchevent-class)\>
const touchEnterEvent
:::

Static factory designed to expose `touchenter` events to event handlers
that are not necessarily instances of [Element](../element-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<TouchEvent> touchEnterEvent =
    const EventStreamProvider<TouchEvent>('touchenter');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/touchEnterEvent-constant.html>
:::
