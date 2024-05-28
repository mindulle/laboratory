[dart:html](../../dart-html/dart-html-library){._links-link}

beforeUnloadEvent constant
==========================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[BeforeUnloadEvent](../beforeunloadevent-class)\>
const beforeUnloadEvent
:::

Static factory designed to expose `beforeunload` events to event
handlers that are not necessarily instances of
[Window](../window-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<BeforeUnloadEvent> beforeUnloadEvent =
    const EventStreamProvider('beforeunload');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/beforeUnloadEvent-constant.html>
:::
