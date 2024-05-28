[dart:html](../../dart-html/dart-html-library){._links-link}

fullscreenErrorEvent constant
=============================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const fullscreenErrorEvent

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.SAFARI)
:::
:::

Static factory designed to expose `fullscreenerror` events to event
handlers that are not necessarily instances of
[Element](../element-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@SupportedBrowser(SupportedBrowser.CHROME)
@SupportedBrowser(SupportedBrowser.SAFARI)
static const EventStreamProvider<Event> fullscreenErrorEvent =
    const EventStreamProvider<Event>('webkitfullscreenerror');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/fullscreenErrorEvent-constant.html>
:::
