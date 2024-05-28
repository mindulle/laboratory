[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

listen method
=============

::: {.section .multi-line-signature}
[StreamSubscription](../../dart-async/streamsubscription-class) listen(

1.  void onData(
    1.  dynamic message

    )?,
2.  {[Function](../../dart-core/function-class)? onError,
3.  void onDone( )?,
4.  [bool](../../dart-core/bool-class)? cancelOnError}

)

::: {.features}
override
:::
:::

Listen for events from [Stream](../../dart-async/stream-class).

See [Stream.listen](../../dart-async/stream/listen).

Note that `onError` and `cancelOnError` are ignored since a
[ReceivePort](../receiveport-class) will never receive an error.

The `onDone` handler will be called when the stream closes. The stream
closes when [close](close) is called.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
StreamSubscription<dynamic> listen(void onData(var message)?,
    {Function? onError, void onDone()?, bool? cancelOnError});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/ReceivePort/listen.html>
:::
