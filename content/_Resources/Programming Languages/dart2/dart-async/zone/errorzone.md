[dart:async](../../dart-async/dart-async-library){._links-link}

errorZone property
==================

::: {#getter .section .multi-line-signature}
[Zone](../zone-class) errorZone
:::

The error zone is responsible for dealing with uncaught errors.

This is the closest parent zone of this zone that provides a
[handleUncaughtError](handleuncaughterror) method.

Asynchronous errors never cross zone boundaries between zones with
different error handlers.

Example:

``` {.language-dart data-language="dart"}
import 'dart:async';

main() {
  var future;
  runZoned(() {
    // The asynchronous error is caught by the custom zone which prints
    // 'asynchronous error'.
    future = Future.error("asynchronous error");
  }, onError: (e) { print(e); });  // Creates a zone with an error handler.
  // The following `catchError` handler is never invoked, because the
  // custom zone created by the call to `runZoned` provides an
  // error handler.
  future.catchError((e) { throw "is never reached"; });
}
```

Note that errors cannot enter a child zone with a different error
handler either:

``` {.language-dart data-language="dart"}
import 'dart:async';

main() {
  runZoned(() {
    // The following asynchronous error is *not* caught by the `catchError`
    // in the nested zone, since errors are not to cross zone boundaries
    // with different error handlers.
    // Instead the error is handled by the current error handler,
    // printing "Caught by outer zone: asynchronous error".
    var future = Future.error("asynchronous error");
    runZoned(() {
      future.catchError((e) { throw "is never reached"; });
    }, onError: (e) { throw "is never reached"; });
  }, onError: (e) { print("Caught by outer zone: $e"); });
}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Zone get errorZone;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone/errorZone.html>
:::
