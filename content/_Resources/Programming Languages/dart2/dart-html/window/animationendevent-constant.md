[dart:html](../../dart-html/dart-html-library){._links-link}

animationEndEvent constant
==========================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[AnimationEvent](../animationevent-class)\>
const animationEndEvent

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME),
\@SupportedBrowser(SupportedBrowser.SAFARI)
:::
:::

Static factory designed to expose `animationend` events to event
handlers that are not necessarily instances of
[Window](../window-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@SupportedBrowser(SupportedBrowser.CHROME)
@SupportedBrowser(SupportedBrowser.SAFARI)
static const EventStreamProvider<AnimationEvent> animationEndEvent =
    const EventStreamProvider<AnimationEvent>('webkitAnimationEnd');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/animationEndEvent-constant.html>
:::
