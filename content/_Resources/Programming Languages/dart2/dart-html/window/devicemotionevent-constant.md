[dart:html](../../dart-html/dart-html-library){._links-link}

deviceMotionEvent constant
==========================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[DeviceMotionEvent](../devicemotionevent-class)\>
const deviceMotionEvent
:::

Static factory designed to expose `devicemotion` events to event
handlers that are not necessarily instances of
[Window](../window-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<DeviceMotionEvent> deviceMotionEvent =
    const EventStreamProvider<DeviceMotionEvent>('devicemotion');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/deviceMotionEvent-constant.html>
:::
