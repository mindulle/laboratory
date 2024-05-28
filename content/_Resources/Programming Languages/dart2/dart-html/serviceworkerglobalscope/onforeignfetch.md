[dart:html](../../dart-html/dart-html-library){._links-link}

onForeignfetch property
=======================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[ForeignFetchEvent](../foreignfetchevent-class)\>
onForeignfetch
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<ForeignFetchEvent> get onForeignfetch =>
    foreignfetchEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ServiceWorkerGlobalScope/onForeignfetch.html>
:::
