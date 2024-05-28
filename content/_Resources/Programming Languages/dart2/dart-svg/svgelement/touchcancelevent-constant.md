[dart:svg](../../dart-svg/dart-svg-library){._links-link}

touchCancelEvent constant
=========================

::: {.section .multi-line-signature}
[EventStreamProvider](../../dart-html/eventstreamprovider-class)\<[TouchEvent](../../dart-html/touchevent-class)\>
const touchCancelEvent
:::

Static factory designed to expose `touchcancel` events to event handlers
that are not necessarily instances of
[Element](../../dart-html/element-class).

See [EventStreamProvider](../../dart-html/eventstreamprovider-class) for
usage information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<TouchEvent> touchCancelEvent =
    const EventStreamProvider<TouchEvent>('touchcancel');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/SvgElement/touchCancelEvent-constant.html>
:::
