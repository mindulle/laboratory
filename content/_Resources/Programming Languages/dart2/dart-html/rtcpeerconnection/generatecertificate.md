[dart:html](../../dart-html/dart-html-library){._links-link}

generateCertificate method
==========================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) generateCertificate(

1.  dynamic keygenAlgorithm

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future generateCertificate(/*AlgorithmIdentifier*/ keygenAlgorithm) =>
    JS('dynamic', 'generateCertificate(#)', keygenAlgorithm);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcPeerConnection/generateCertificate.html>
:::
