[dart:io](../../dart-io/dart-io-library){._links-link}

redirect method
===============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) redirect(

1.  [Uri](../../dart-core/uri-class) location,
2.  {[int](../../dart-core/int-class) status =
    HttpStatus.movedTemporarily}

)
:::

Respond with a redirect to `location`.

The URI in `location` should be absolute, but there are no checks to
enforce that.

By default the HTTP status code `HttpStatus.movedTemporarily` (`302`) is
used for the redirect, but an alternative one can be specified using the
`status` argument.

This method will also call `close`, and the returned future is the
future returned by `close`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future redirect(Uri location, {int status = HttpStatus.movedTemporarily});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpResponse/redirect.html>
:::
