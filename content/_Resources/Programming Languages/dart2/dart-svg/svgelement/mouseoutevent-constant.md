[dart:svg](../../dart-svg/dart-svg-library){._links-link}

mouseOutEvent constant
======================

::: {.section .multi-line-signature}
[EventStreamProvider](../../dart-html/eventstreamprovider-class)\<[MouseEvent](../../dart-html/mouseevent-class)\>
const mouseOutEvent
:::

Static factory designed to expose `mouseout` events to event handlers
that are not necessarily instances of
[Element](../../dart-html/element-class).

See [EventStreamProvider](../../dart-html/eventstreamprovider-class) for
usage information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<MouseEvent> mouseOutEvent =
    const EventStreamProvider<MouseEvent>('mouseout');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/SvgElement/mouseOutEvent-constant.html>
:::
