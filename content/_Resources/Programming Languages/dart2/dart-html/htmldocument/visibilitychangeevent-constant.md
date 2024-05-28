[dart:html](../../dart-html/dart-html-library){._links-link}

visibilityChangeEvent constant
==============================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const visibilityChangeEvent

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.FIREFOX),
\@SupportedBrowser(SupportedBrowser.IE, \'10\')
:::
:::

Static factory designed to expose `visibilitychange` events to event
handlers that are not necessarily instances of
[Document](../document-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@SupportedBrowser(SupportedBrowser.CHROME)
@SupportedBrowser(SupportedBrowser.FIREFOX)
@SupportedBrowser(SupportedBrowser.IE, '10')
static const EventStreamProvider<Event> visibilityChangeEvent =
    const _CustomEventStreamProvider<Event>(
        _determineVisibilityChangeEventType);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HtmlDocument/visibilityChangeEvent-constant.html>
:::
