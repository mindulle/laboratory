[dart:html](../../dart-html/dart-html-library){._links-link}

watchAvailability method
========================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[int](../../dart-core/int-class)\>
watchAvailability(

1.  [RemotePlaybackAvailabilityCallback](../remoteplaybackavailabilitycallback)
    callback

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<int> watchAvailability(RemotePlaybackAvailabilityCallback callback) =>
    promiseToFuture<int>(JS("", "#.watchAvailability(#)", this, callback));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RemotePlayback/watchAvailability.html>
:::
