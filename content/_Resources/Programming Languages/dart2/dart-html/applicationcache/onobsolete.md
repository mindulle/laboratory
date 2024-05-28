[dart:html](../../dart-html/dart-html-library){._links-link}

onObsolete property
===================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[Event](../event-class)\>
onObsolete
:::

Stream of `obsolete` events handled by this
[ApplicationCache](../applicationcache-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<Event> get onObsolete => obsoleteEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ApplicationCache/onObsolete.html>
:::
