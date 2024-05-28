[dart:html](../../dart-html/dart-html-library){._links-link}

beforePasteEvent constant
=========================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const beforePasteEvent
:::

Static factory designed to expose `beforepaste` events to event handlers
that are not necessarily instances of [Element](../element-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> beforePasteEvent =
    const EventStreamProvider<Event>('beforepaste');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/beforePasteEvent-constant.html>
:::
