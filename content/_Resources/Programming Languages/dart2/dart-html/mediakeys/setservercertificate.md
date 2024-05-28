[dart:html](../../dart-html/dart-html-library){._links-link}

setServerCertificate method
===========================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) setServerCertificate(

1.  dynamic serverCertificate

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future setServerCertificate(/*BufferSource*/ serverCertificate) =>
    promiseToFuture(
        JS("", "#.setServerCertificate(#)", this, serverCertificate));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaKeys/setServerCertificate.html>
:::
