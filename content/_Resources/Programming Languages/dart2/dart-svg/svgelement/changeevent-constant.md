[dart:svg](../../dart-svg/dart-svg-library){._links-link}

changeEvent constant
====================

::: {.section .multi-line-signature}
[EventStreamProvider](../../dart-html/eventstreamprovider-class)\<[Event](../../dart-html/event-class)\>
const changeEvent
:::

Static factory designed to expose `change` events to event handlers that
are not necessarily instances of
[Element](../../dart-html/element-class).

See [EventStreamProvider](../../dart-html/eventstreamprovider-class) for
usage information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> changeEvent =
    const EventStreamProvider<Event>('change');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/SvgElement/changeEvent-constant.html>
:::
