[dart:html](../../dart-html/dart-html-library){._links-link}

forTarget method
================

::: {.section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<T\> forTarget(

1.  [EventTarget](../eventtarget-class)? e,
2.  {[bool](../../dart-core/bool-class) useCapture = false}

)
:::

Gets a [Stream](../../dart-async/stream-class) for this event type, on
the specified target.

This will always return a broadcast stream so multiple listeners can be
used simultaneously.

This may be used to capture DOM events:

``` {.language-dart data-language="dart"}
Element.keyDownEvent.forTarget(element, useCapture: true).listen(...);

// Alternate method:
Element.keyDownEvent.forTarget(element).capture(...);
```

Or for listening to an event which will bubble through the DOM tree:

``` {.language-dart data-language="dart"}
MediaElement.pauseEvent.forTarget(document.body).listen(...);
```

See also:

-   [EventTarget.addEventListener](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
    from MDN.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<T> forTarget(EventTarget? e, {bool useCapture: false}) =>
    new _EventStream<T>(e, _eventType, useCapture);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/EventStreamProvider/forTarget.html>
:::
