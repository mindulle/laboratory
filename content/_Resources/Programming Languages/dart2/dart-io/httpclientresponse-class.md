[dart:io](../dart-io/dart-io-library){._links-link}

HttpClientResponse class
========================

HTTP response for a client connection.

The body of a [HttpClientResponse](httpclientresponse-class) object is a
[Stream](../dart-async/stream-class) of data from the server. Use
[Stream](../dart-async/stream-class) methods like
[Stream.transform](../dart-async/stream/transform) and
[Stream.join](../dart-async/stream/join) to access the data.

``` {.language-dart data-language="dart"}
var client = HttpClient();
try {
  HttpClientRequest request = await client.get('localhost', 80, '/file.txt');
  HttpClientResponse response = await request.close();
  final stringData = await response.transform(utf8.decoder).join();
  print(stringData);
} finally {
  client.close();
}
```

Implemented types

:   -   [Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

Constructors
------------

[HttpClientResponse](httpclientresponse/httpclientresponse)()

Properties {#instance-properties}
----------

[certificate](httpclientresponse/certificate) →
[X509Certificate](x509certificate-class)?

::: {.features}
read-only
:::

Returns the certificate of the HTTPS server providing the response.
Returns null if the connection is not a secure TLS or SSL connection.

[compressionState](httpclientresponse/compressionstate) →
[HttpClientResponseCompressionState](httpclientresponsecompressionstate)

::: {.features}
\@Since(\"2.4\"), read-only
:::

The compression state of the response.

[connectionInfo](httpclientresponse/connectioninfo) →
[HttpConnectionInfo](httpconnectioninfo-class)?

::: {.features}
read-only
:::

Gets information about the client connection. Returns `null` if the
socket is not available.

[contentLength](httpclientresponse/contentlength) →
[int](../dart-core/int-class)

::: {.features}
read-only
:::

Returns the content length of the response body. Returns -1 if the size
of the response body is not known in advance.

[cookies](httpclientresponse/cookies) →
[List](../dart-core/list-class)\<[Cookie](cookie-class)\>

::: {.features}
read-only
:::

Cookies set by the server (from the \'set-cookie\' header).

[first](../dart-async/stream/first) →
[Future](../dart-async/future-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
read-only, inherited
:::

The first element of this stream.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[headers](httpclientresponse/headers) → [HttpHeaders](httpheaders-class)

::: {.features}
read-only
:::

Returns the client response headers.

[isBroadcast](../dart-async/stream/isbroadcast) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this stream is a broadcast stream.

[isEmpty](../dart-async/stream/isempty) →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
read-only, inherited
:::

Whether this stream contains any elements.

[isRedirect](httpclientresponse/isredirect) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Returns whether the status code is one of the normal redirect codes
[HttpStatus.movedPermanently](../dart-html/httpstatus/movedpermanently-constant),
[HttpStatus.found](../dart-html/httpstatus/found-constant),
[HttpStatus.movedTemporarily](../dart-html/httpstatus/movedtemporarily-constant),
[HttpStatus.seeOther](../dart-html/httpstatus/seeother-constant) and
[HttpStatus.temporaryRedirect](../dart-html/httpstatus/temporaryredirect-constant).

[last](../dart-async/stream/last) →
[Future](../dart-async/future-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
read-only, inherited
:::

The last element of this stream.

[length](../dart-async/stream/length) →
[Future](../dart-async/future-class)\<[int](../dart-core/int-class)\>

::: {.features}
read-only, inherited
:::

The number of elements in this stream.

[persistentConnection](httpclientresponse/persistentconnection) →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Gets the persistent connection state returned by the server.

[reasonPhrase](httpclientresponse/reasonphrase) →
[String](../dart-core/string-class)

::: {.features}
read-only
:::

Returns the reason phrase associated with the status code.

[redirects](httpclientresponse/redirects) →
[List](../dart-core/list-class)\<[RedirectInfo](redirectinfo-class)\>

::: {.features}
read-only
:::

Returns the series of redirects this connection has been through. The
list will be empty if no redirects were followed.
[redirects](httpclientresponse/redirects) will be updated both in the
case of an automatic and a manual redirect.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[single](../dart-async/stream/single) →
[Future](../dart-async/future-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
read-only, inherited
:::

The single element of this stream.

[statusCode](httpclientresponse/statuscode) →
[int](../dart-core/int-class)

::: {.features}
read-only
:::

Returns the status code.

Methods {#instance-methods}
-------

[any](../dart-async/stream/any)([bool](../dart-core/bool-class)
test([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
element)) →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Checks whether `test` accepts any element provided by this stream.

[asBroadcastStream](../dart-async/stream/asbroadcaststream)({void
onListen([StreamSubscription](../dart-async/streamsubscription-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
subscription)?, void
onCancel([StreamSubscription](../dart-async/streamsubscription-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
subscription)?}) →
[Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
inherited
:::

Returns a multi-subscription stream that produces the same events as
this.

[asyncExpand](../dart-async/stream/asyncexpand)\<E\>([Stream](../dart-async/stream-class)\<E\>?
convert([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
event)) → [Stream](../dart-async/stream-class)\<E\>

::: {.features}
inherited
:::

Transforms each element into a sequence of asynchronous events.

[asyncMap](../dart-async/stream/asyncmap)\<E\>([FutureOr](../dart-async/futureor-class)\<E\>
convert([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
event)) → [Stream](../dart-async/stream-class)\<E\>

::: {.features}
inherited
:::

Creates a new stream with each data event of this stream asynchronously
mapped to a new event.

[cast](../dart-async/stream/cast)\<R\>() →
[Stream](../dart-async/stream-class)\<R\>

::: {.features}
inherited
:::

Adapt this stream to be a `Stream<R>`.

[contains](../dart-async/stream/contains)([Object](../dart-core/object-class)?
needle) →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Returns whether `needle` occurs in the elements provided by this stream.

[detachSocket](httpclientresponse/detachsocket)() →
[Future](../dart-async/future-class)\<[Socket](socket-class)\>

Detach the underlying socket from the HTTP client. When the socket is
detached the HTTP client will no longer perform any operations on it.

[distinct](../dart-async/stream/distinct)(\[[bool](../dart-core/bool-class)
equals([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
previous,
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
next)?\]) →
[Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
inherited
:::

Skips data events if they are equal to the previous data event.

[drain](../dart-async/stream/drain)\<E\>(\[E? futureValue\]) →
[Future](../dart-async/future-class)\<E\>

::: {.features}
inherited
:::

Discards all data on this stream, but signals when it is done or an
error occurred.

[elementAt](../dart-async/stream/elementat)([int](../dart-core/int-class)
index) →
[Future](../dart-async/future-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
inherited
:::

Returns the value of the `index`th data event of this stream.

[every](../dart-async/stream/every)([bool](../dart-core/bool-class)
test([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
element)) →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Checks whether `test` accepts all elements provided by this stream.

[expand](../dart-async/stream/expand)\<S\>([Iterable](../dart-core/iterable-class)\<S\>
convert([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
element)) → [Stream](../dart-async/stream-class)\<S\>

::: {.features}
inherited
:::

Transforms each element of this stream into a sequence of elements.

[firstWhere](../dart-async/stream/firstwhere)([bool](../dart-core/bool-class)
test([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
element),
{[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
orElse()?}) →
[Future](../dart-async/future-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
inherited
:::

Finds the first element of this stream matching `test`.

[fold](../dart-async/stream/fold)\<S\>(S initialValue, S combine(S
previous,
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
element)) → [Future](../dart-async/future-class)\<S\>

::: {.features}
inherited
:::

Combines a sequence of values by repeatedly applying `combine`.

[forEach](../dart-async/stream/foreach)(void
action([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
element)) → [Future](../dart-async/future-class)

::: {.features}
inherited
:::

Executes `action` on each element of this stream.

[handleError](../dart-async/stream/handleerror)([Function](../dart-core/function-class)
onError, {[bool](../dart-core/bool-class) test(dynamic error)?}) →
[Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
inherited
:::

Creates a wrapper Stream that intercepts some errors from this stream.

[join](../dart-async/stream/join)(\[[String](../dart-core/string-class)
separator = \"\"\]) →
[Future](../dart-async/future-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Combines the string representation of elements into a single string.

[lastWhere](../dart-async/stream/lastwhere)([bool](../dart-core/bool-class)
test([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
element),
{[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
orElse()?}) →
[Future](../dart-async/future-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
inherited
:::

Finds the last element in this stream matching `test`.

[listen](../dart-async/stream/listen)(void
onData([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
event)?, {[Function](../dart-core/function-class)? onError, void
onDone()?, [bool](../dart-core/bool-class)? cancelOnError}) →
[StreamSubscription](../dart-async/streamsubscription-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
inherited
:::

Adds a subscription to this stream.

[map](../dart-async/stream/map)\<S\>(S
convert([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
event)) → [Stream](../dart-async/stream-class)\<S\>

::: {.features}
inherited
:::

Transforms each element of this stream into a new stream event.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[pipe](../dart-async/stream/pipe)([StreamConsumer](../dart-async/streamconsumer-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
streamConsumer) → [Future](../dart-async/future-class)

::: {.features}
inherited
:::

Pipes the events of this stream into `streamConsumer`.

[redirect](httpclientresponse/redirect)(\[[String](../dart-core/string-class)?
method, [Uri](../dart-core/uri-class)? url,
[bool](../dart-core/bool-class)? followLoops\]) →
[Future](../dart-async/future-class)\<[HttpClientResponse](httpclientresponse-class)\>

Redirects this connection to a new URL. The default value for `method`
is the method for the current request. The default value for `url` is
the value of the
[HttpHeaders.locationHeader](httpheaders/locationheader-constant) header
of the current response. All body data must have been read from the
current response before calling [redirect](httpclientresponse/redirect).

[reduce](../dart-async/stream/reduce)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
combine([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
previous,
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
element)) →
[Future](../dart-async/future-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
inherited
:::

Combines a sequence of values by repeatedly applying `combine`.

[singleWhere](../dart-async/stream/singlewhere)([bool](../dart-core/bool-class)
test([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
element),
{[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
orElse()?}) →
[Future](../dart-async/future-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
inherited
:::

Finds the single element in this stream matching `test`.

[skip](../dart-async/stream/skip)([int](../dart-core/int-class) count) →
[Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
inherited
:::

Skips the first `count` data events from this stream.

[skipWhile](../dart-async/stream/skipwhile)([bool](../dart-core/bool-class)
test([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
element)) →
[Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
inherited
:::

Skip data events from this stream while they are matched by `test`.

[take](../dart-async/stream/take)([int](../dart-core/int-class) count) →
[Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
inherited
:::

Provides at most the first `count` data events of this stream.

[takeWhile](../dart-async/stream/takewhile)([bool](../dart-core/bool-class)
test([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
element)) →
[Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
inherited
:::

Forwards data events while `test` is successful.

[timeout](../dart-async/stream/timeout)([Duration](../dart-core/duration-class)
timeLimit, {void
onTimeout([EventSink](../dart-async/eventsink-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
sink)?}) →
[Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
inherited
:::

Creates a new stream with the same events as this stream.

[toList](../dart-async/stream/tolist)() →
[Future](../dart-async/future-class)\<[List](../dart-core/list-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>\>

::: {.features}
inherited
:::

Collects all elements of this stream in a `List`.

[toSet](../dart-async/stream/toset)() →
[Future](../dart-async/future-class)\<[Set](../dart-core/set-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>\>

::: {.features}
inherited
:::

Collects the data of this stream in a `Set`.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[transform](../dart-async/stream/transform)\<S\>([StreamTransformer](../dart-async/streamtransformer-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
S\> streamTransformer) → [Stream](../dart-async/stream-class)\<S\>

::: {.features}
inherited
:::

Applies `streamTransformer` to this stream.

[where](../dart-async/stream/where)([bool](../dart-core/bool-class)
test([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
event)) →
[Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
inherited
:::

Creates a new stream from this stream that discards some elements.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClientResponse-class.html>
:::
