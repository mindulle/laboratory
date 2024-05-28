[dart:html](../../dart-html/dart-html-library){._links-link}

addIceCandidate method
======================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) addIceCandidate(

1.  [Object](../../dart-core/object-class) candidate,
2.  \[[VoidCallback](../voidcallback)? successCallback,
3.  [RtcPeerConnectionErrorCallback](../rtcpeerconnectionerrorcallback)?
    failureCallback\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future addIceCandidate(Object candidate,
        [VoidCallback? successCallback,
        RtcPeerConnectionErrorCallback? failureCallback]) =>
    promiseToFuture(JS("", "#.addIceCandidate(#, #, #)", this, candidate,
        successCallback, failureCallback));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcPeerConnection/addIceCandidate.html>
:::
