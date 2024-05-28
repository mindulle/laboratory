[dart:async](../../dart-async/dart-async-library){._links-link}

onDone method
=============

::: {.section .multi-line-signature}
void onDone(

1.  void handleDone( )?

)
:::

Replaces the done event handler of this subscription.

The `handleDone` function is called when the stream closes. The value
may be `null`, in which case no function is called.

This method replaces the current handler set by the invocation of
[Stream.listen](../stream/listen), by calling [asFuture](asfuture), or
by a previous call to [onDone](ondone).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void onDone(void handleDone()?);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamSubscription/onDone.html>
:::
