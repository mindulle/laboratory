[dart:html](../../dart-html/dart-html-library){._links-link}

capture method
==============

::: {.section .multi-line-signature}
[StreamSubscription](../../dart-async/streamsubscription-class)\<T\>
capture(

1.  void onData(
    1.  T event

    )

)
:::

Adds a capturing subscription to this stream.

If the target of the event is a descendant of the element from which
this stream derives then `onData` is called before the event propagates
down to the target. This is the opposite of bubbling behavior, where the
event is first processed for the event target and then bubbles upward.

Other resources
---------------

-   [Event
    Capture](http://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-flow-capture)
    from the W3C DOM Events specification.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
StreamSubscription<T> capture(void onData(T event));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ElementStream/capture.html>
:::
