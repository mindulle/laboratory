[dart:html](../../dart-html/dart-html-library){._links-link}

invalidEvent constant
=====================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const invalidEvent
:::

Static factory designed to expose `invalid` events to event handlers
that are not necessarily instances of [Element](../element-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> invalidEvent =
    const EventStreamProvider<Event>('invalid');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/invalidEvent-constant.html>
:::
