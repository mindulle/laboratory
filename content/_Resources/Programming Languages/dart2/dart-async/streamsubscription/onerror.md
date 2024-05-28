[dart:async](../../dart-async/dart-async-library){._links-link}

onError method
==============

::: {.section .multi-line-signature}
void onError(

1.  [Function](../../dart-core/function-class)? handleError

)
:::

Replaces the error event handler of this subscription.

The `handleError` function must be able to be called with either one
positional argument, or with two positional arguments where the seconds
is always a [StackTrace](../../dart-core/stacktrace-class).

The `handleError` argument may be `null`, in which case further error
events are considered *unhandled*, and will be reported to
[Zone.handleUncaughtError](../zone/handleuncaughterror).

The provided function is called for all error events from the stream
subscription.

This method replaces the current handler set by the invocation of
[Stream.listen](../stream/listen), by calling [asFuture](asfuture), or
by a previous call to [onError](onerror).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void onError(Function? handleError);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamSubscription/onError.html>
:::
