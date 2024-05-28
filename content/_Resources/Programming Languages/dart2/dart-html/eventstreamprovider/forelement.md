[dart:html](../../dart-html/dart-html-library){._links-link}

forElement method
=================

::: {.section .multi-line-signature}
[ElementStream](../elementstream-class)\<T\> forElement(

1.  [Element](../element-class) e,
2.  {[bool](../../dart-core/bool-class) useCapture = false}

)
:::

Gets a [Stream](../../dart-async/stream-class) for this event type, on
the specified element.

This will always return a broadcast stream so multiple listeners can be
used simultaneously.

This may be used to capture DOM events:

``` {.language-dart data-language="dart"}
Element.keyDownEvent.forElement(element, useCapture: true).listen(...);

// Alternate method:
Element.keyDownEvent.forElement(element).capture(...);
```

Or for listening to an event which will bubble through the DOM tree:

``` {.language-dart data-language="dart"}
MediaElement.pauseEvent.forElement(document.body).listen(...);
```

See also:

-   [EventTarget.addEventListener](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
    from MDN.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ElementStream<T> forElement(Element e, {bool useCapture: false}) {
  return new _ElementEventStreamImpl<T>(e, _eventType, useCapture);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/EventStreamProvider/forElement.html>
:::
