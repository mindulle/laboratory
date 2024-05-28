[dart:io](../../dart-io/dart-io-library){._links-link}

abort method
============

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.10\")

</div>

void abort(

1.  \[[Object](../../dart-core/object-class)? exception,
2.  [StackTrace](../../dart-core/stacktrace-class)? stackTrace\]

)

::: {.features}
\@Since(\"2.10\")
:::
:::

Aborts the client connection.

If the connection has not yet completed, the request is aborted and the
[done](done) future (also returned by [close](close)) is completed with
the provided `exception` and `stackTrace`. If `exception` is omitted, it
defaults to an [HttpException](../httpexception-class), and if
`stackTrace` is omitted, it defaults to
[StackTrace.empty](../../dart-core/stacktrace/empty-constant).

If the [done](done) future has already completed, aborting has no
effect.

Using the [IOSink](../iosink-class) methods (e.g.,
[write](../iosink/write) and [add](../iosink/add)) has no effect after
the request has been aborted

``` {.language-dart data-language="dart"}
var client = HttpClient();
HttpClientRequest request = await client.get('localhost', 80, '/file.txt');
request.write('request content');
Timer(Duration(seconds: 1), () {
  request.abort();
});
request.close().then((response) {
  // If response comes back before abort, this callback will be called.
}, onError: (e) {
  // If abort() called before response is available, onError will fire.
});
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.10")
void abort([Object? exception, StackTrace? stackTrace]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClientRequest/abort.html>
:::
