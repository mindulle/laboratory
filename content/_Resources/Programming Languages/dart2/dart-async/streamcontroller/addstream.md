[dart:async](../../dart-async/dart-async-library){._links-link}

addStream method
================

::: {.section .multi-line-signature}
[Future](../future-class) addStream(

1.  [Stream](../stream-class)\<T\> source,
2.  {[bool](../../dart-core/bool-class)? cancelOnError}

)

::: {.features}
override
:::
:::

Receives events from `source` and puts them into this controller\'s
stream.

Returns a future which completes when the source stream is done.

Events must not be added directly to this controller using [add](add),
[addError](adderror), [close](close) or [addStream](addstream), until
the returned future is complete.

Data and error events are forwarded to this controller\'s stream. A done
event on the source will end the `addStream` operation and complete the
returned future.

If `cancelOnError` is `true`, only the first error on `source` is
forwarded to the controller\'s stream, and the `addStream` ends after
this. If `cancelOnError` is false, all errors are forwarded and only a
done event will end the `addStream`. If `cancelOnError` is omitted or
`null`, it defaults to `false`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future addStream(Stream<T> source, {bool? cancelOnError});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamController/addStream.html>
:::
