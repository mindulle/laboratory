[dart:html](../../dart-html/dart-html-library){._links-link}

beforeCopyEvent constant
========================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const beforeCopyEvent
:::

Static factory designed to expose `beforecopy` events to event handlers
that are not necessarily instances of [Element](../element-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> beforeCopyEvent =
    const EventStreamProvider<Event>('beforecopy');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/beforeCopyEvent-constant.html>
:::
