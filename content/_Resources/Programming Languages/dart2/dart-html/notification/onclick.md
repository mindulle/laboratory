[dart:html](../../dart-html/dart-html-library){._links-link}

onClick property
================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[Event](../event-class)\>
onClick
:::

Stream of `click` events handled by this
[Notification](../notification-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<Event> get onClick => clickEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Notification/onClick.html>
:::
