[dart:io](../../dart-io/dart-io-library){._links-link}

addStream method
================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) addStream(

1.  [Stream](../../dart-async/stream-class)\<[List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>\>
    stream

)

::: {.features}
override
:::
:::

Adds all elements of the given `stream`.

Returns a [Future](../../dart-async/future-class) that completes when
all elements of the given `stream` have been added.

If the stream contains an error, the `addStream` ends at the error, and
the returned future completes with that error.

This function must not be called when a stream is currently being added
using this function.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future addStream(Stream<List<int>> stream);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOSink/addStream.html>
:::
