[dart:async](../../dart-async/dart-async-library){._links-link}

asFuture\<E\> method
====================

::: {.section .multi-line-signature}
[Future](../future-class)\<E\> asFuture\<E\>(

1.  \[E? futureValue\]

)
:::

Returns a future that handles the [onDone](ondone) and
[onError](onerror) callbacks.

This method *overwrites* the existing [onDone](ondone) and
[onError](onerror) callbacks with new ones that complete the returned
future.

In case of an error the subscription will automatically cancel (even
when it was listening with `cancelOnError` set to `false`).

In case of a `done` event the future completes with the given
`futureValue`.

If `futureValue` is omitted, the value `null as E` is used as a default.
If `E` is not nullable, this will throw immediately when
[asFuture](asfuture) is called.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<E> asFuture<E>([E? futureValue]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamSubscription/asFuture.html>
:::
