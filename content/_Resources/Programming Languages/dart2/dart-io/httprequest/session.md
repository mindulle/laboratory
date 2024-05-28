[dart:io](../../dart-io/dart-io-library){._links-link}

session property
================

::: {#getter .section .multi-line-signature}
[HttpSession](../httpsession-class) session
:::

The session for the given request.

If the session is being initialized by this call,
[HttpSession.isNew](../httpsession/isnew) is true for the returned
session. See [HttpServer.sessionTimeout](../httpserver/sessiontimeout)
on how to change default timeout.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
HttpSession get session;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpRequest/session.html>
:::
