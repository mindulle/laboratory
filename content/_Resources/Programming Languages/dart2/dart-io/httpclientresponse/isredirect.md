[dart:io](../../dart-io/dart-io-library){._links-link}

isRedirect property
===================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) isRedirect
:::

Returns whether the status code is one of the normal redirect codes
[HttpStatus.movedPermanently](../../dart-html/httpstatus/movedpermanently-constant),
[HttpStatus.found](../../dart-html/httpstatus/found-constant),
[HttpStatus.movedTemporarily](../../dart-html/httpstatus/movedtemporarily-constant),
[HttpStatus.seeOther](../../dart-html/httpstatus/seeother-constant) and
[HttpStatus.temporaryRedirect](../../dart-html/httpstatus/temporaryredirect-constant).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isRedirect;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClientResponse/isRedirect.html>
:::
