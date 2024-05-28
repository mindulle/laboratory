[dart:html](../../dart-html/dart-html-library){._links-link}

onKeyDown method
================

::: {.section .multi-line-signature}
[CustomStream](../customstream-class)\<[KeyEvent](../keyevent-class)\>
onKeyDown(

1.  [EventTarget](../eventtarget-class) target

)
:::

Named constructor to produce a stream for onKeyDown events.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static CustomStream<KeyEvent> onKeyDown(EventTarget target) =>
    new _KeyboardEventHandler('keydown').forTarget(target);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/KeyboardEventStream/onKeyDown.html>
:::
