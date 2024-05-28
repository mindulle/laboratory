[dart:html](../../dart-html/dart-html-library){._links-link}

getEventType method
===================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) getEventType(

1.  [EventTarget](../eventtarget-class) target

)
:::

Gets the type of the event which this would listen for on the specified
event target.

The target is necessary because some browsers may use different event
names for the same purpose and the target allows differentiating browser
support.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String getEventType(EventTarget target) {
  return _eventType;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/EventStreamProvider/getEventType.html>
:::
