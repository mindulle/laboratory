[dart:async](../../dart-async/dart-async-library){._links-link}

onData method
=============

::: {.section .multi-line-signature}
void onData(

1.  void handleData(
    1.  T data

    )?

)
:::

Replaces the data event handler of this subscription.

The `handleData` function is called for each data event of the stream
after this function is called. If `handleData` is `null`, data events
are ignored.

This method replaces the current handler set by the invocation of
[Stream.listen](../stream/listen) or by a previous call to
[onData](ondata).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void onData(void handleData(T data)?);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamSubscription/onData.html>
:::
