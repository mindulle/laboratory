[dart:html](../../dart-html/dart-html-library){._links-link}

webGlContextRestoredEvent constant
==================================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[ContextEvent](../../dart-web_gl/contextevent-class)\>
const webGlContextRestoredEvent
:::

Static factory designed to expose `webglcontextrestored` events to event
handlers that are not necessarily instances of
[CanvasElement](../canvaselement-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<gl.ContextEvent> webGlContextRestoredEvent =
    const EventStreamProvider<gl.ContextEvent>('webglcontextrestored');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasElement/webGlContextRestoredEvent-constant.html>
:::
