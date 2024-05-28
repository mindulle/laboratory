[dart:io](../dart-io/dart-io-library){._links-link}

HttpServer class
================

A server that delivers content, such as web pages, using the HTTP
protocol.

Note: [HttpServer](httpserver-class) provides low-level HTTP
functionality. We recommend users evaluate the high-level APIs discussed
at [Write HTTP servers](https://dart.dev/tutorials/server/httpserver) on
[dart.dev](https://dart.dev/).

`HttpServer` is a [Stream](../dart-async/stream-class) that provides
[HttpRequest](httprequest-class) objects. Each `HttpRequest` has an
associated [HttpResponse](httpresponse-class) object. The server
responds to a request by writing to that
[HttpResponse](httpresponse-class) object. The following example shows
how to bind an `HttpServer` to an IPv6
[InternetAddress](internetaddress-class) on port 80 (the standard port
for HTTP servers) and how to listen for requests. Port 80 is the default
HTTP port. However, on most systems accessing this requires super-user
privileges. For local testing consider using a non-reserved port (1024
and above).

``` {.language-dart data-language="dart"}
import 'dart:io';

void main() async {
  var server = await HttpServer.bind(InternetAddress.anyIPv6, 80);
  await server.forEach((HttpRequest request) {
    request.response.write('Hello, world!');
    request.response.close();
  });
}
```

Incomplete requests, in which all or part of the header is missing, are
ignored, and no exceptions or [HttpRequest](httprequest-class) objects
are generated for them. Likewise, when writing to an
[HttpResponse](httpresponse-class), any [Socket](socket-class)
exceptions are ignored and any future writes are ignored.

The [HttpRequest](httprequest-class) exposes the request headers and
provides the request body, if it exists, as a Stream of data. If the
body is unread, it is drained when the server writes to the HttpResponse
or closes it.

Bind with a secure HTTPS connection
-----------------------------------

Use [bindSecure](httpserver/bindsecure) to create an HTTPS server.

The server presents a certificate to the client. The certificate chain
and the private key are set in the
[SecurityContext](securitycontext-class) object that is passed to
[bindSecure](httpserver/bindsecure).

``` {.language-dart data-language="dart"}
import 'dart:io';

void main() async {
  var chain =
      Platform.script.resolve('certificates/server_chain.pem').toFilePath();
  var key = Platform.script.resolve('certificates/server_key.pem').toFilePath();
  var context = SecurityContext()
    ..useCertificateChain(chain)
    ..usePrivateKey(key, password: 'dartdart');
  var server =
      await HttpServer.bindSecure(InternetAddress.anyIPv6, 443, context);
  await server.forEach((HttpRequest request) {
    request.response.write('Hello, world!');
    request.response.close();
  });
}
```

The certificates and keys are PEM files, which can be created and
managed with the tools in OpenSSL.

Implemented types

:   -   [Stream](../dart-async/stream-class)\<[HttpRequest](httprequest-class)\>

Constructors
------------

[HttpServer.listenOn](httpserver/httpserver.listenon)([ServerSocket](serversocket-class)
serverSocket)

::: {.constructor-modifier .features}
factory
:::

Attaches the HTTP server to an existing
[ServerSocket](serversocket-class). When the
[HttpServer](httpserver-class) is closed, the
[HttpServer](httpserver-class) will just detach itself, closing current
connections but not closing `serverSocket`.

Properties {#instance-properties}
----------

[address](httpserver/address) → [InternetAddress](internetaddress-class)

::: {.features}
read-only
:::

The address that the server is listening on.

[autoCompress](httpserver/autocompress) ↔
[bool](../dart-core/bool-class)

::: {.features}
read / write
:::

Whether the [HttpServer](httpserver-class) should compress the content,
if possible.

[defaultResponseHeaders](httpserver/defaultresponseheaders) →
[HttpHeaders](httpheaders-class)

::: {.features}
read-only
:::

Default set of headers added to all response objects.

[first](../dart-async/stream/first) →
[Future](../dart-async/future-class)\<[HttpRequest](httprequest-class)\>

::: {.features}
read-only, inherited
:::

The first element of this stream.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[idleTimeout](httpserver/idletimeout) ↔
[Duration](../dart-core/duration-class)?

::: {.features}
read / write
:::

Gets or sets the timeout used for idle keep-alive connections. If no
further request is seen within [idleTimeout](httpserver/idletimeout)
after the previous request was completed, the connection is dropped.

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

[last](../dart-async/stream/last) →
[Future](../dart-async/future-class)\<[HttpRequest](httprequest-class)\>

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

[port](httpserver/port) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

The port that the server is listening on.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[serverHeader](httpserver/serverheader) ↔
[String](../dart-core/string-class)?

::: {.features}
read / write
:::

Gets and sets the default value of the `Server` header for all responses
generated by this [HttpServer](httpserver-class).

[sessionTimeout](httpserver/sessiontimeout) ←
[int](../dart-core/int-class)

::: {.features}
write-only
:::

Sets the timeout, in seconds, for sessions of this
[HttpServer](httpserver-class).

[single](../dart-async/stream/single) →
[Future](../dart-async/future-class)\<[HttpRequest](httprequest-class)\>

::: {.features}
read-only, inherited
:::

The single element of this stream.

Methods {#instance-methods}
-------

[any](../dart-async/stream/any)([bool](../dart-core/bool-class)
test([HttpRequest](httprequest-class) element)) →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Checks whether `test` accepts any element provided by this stream.

[asBroadcastStream](../dart-async/stream/asbroadcaststream)({void
onListen([StreamSubscription](../dart-async/streamsubscription-class)\<[HttpRequest](httprequest-class)\>
subscription)?, void
onCancel([StreamSubscription](../dart-async/streamsubscription-class)\<[HttpRequest](httprequest-class)\>
subscription)?}) →
[Stream](../dart-async/stream-class)\<[HttpRequest](httprequest-class)\>

::: {.features}
inherited
:::

Returns a multi-subscription stream that produces the same events as
this.

[asyncExpand](../dart-async/stream/asyncexpand)\<E\>([Stream](../dart-async/stream-class)\<E\>?
convert([HttpRequest](httprequest-class) event)) →
[Stream](../dart-async/stream-class)\<E\>

::: {.features}
inherited
:::

Transforms each element into a sequence of asynchronous events.

[asyncMap](../dart-async/stream/asyncmap)\<E\>([FutureOr](../dart-async/futureor-class)\<E\>
convert([HttpRequest](httprequest-class) event)) →
[Stream](../dart-async/stream-class)\<E\>

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

[close](httpserver/close)({[bool](../dart-core/bool-class) force =
false}) → [Future](../dart-async/future-class)

Permanently stops this [HttpServer](httpserver-class) from listening for
new connections. This closes the [Stream](../dart-async/stream-class) of
[HttpRequest](httprequest-class)s with a done event. The returned future
completes when the server is stopped. For a server started using
[bind](httpserver/bind) or [bindSecure](httpserver/bindsecure) this
means that the port listened on no longer in use.

[connectionsInfo](httpserver/connectionsinfo)() →
[HttpConnectionsInfo](httpconnectionsinfo-class)

A [HttpConnectionsInfo](httpconnectionsinfo-class) object summarizing
the number of current connections handled by the server.

[contains](../dart-async/stream/contains)([Object](../dart-core/object-class)?
needle) →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Returns whether `needle` occurs in the elements provided by this stream.

[distinct](../dart-async/stream/distinct)(\[[bool](../dart-core/bool-class)
equals([HttpRequest](httprequest-class) previous,
[HttpRequest](httprequest-class) next)?\]) →
[Stream](../dart-async/stream-class)\<[HttpRequest](httprequest-class)\>

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
[Future](../dart-async/future-class)\<[HttpRequest](httprequest-class)\>

::: {.features}
inherited
:::

Returns the value of the `index`th data event of this stream.

[every](../dart-async/stream/every)([bool](../dart-core/bool-class)
test([HttpRequest](httprequest-class) element)) →
[Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>

::: {.features}
inherited
:::

Checks whether `test` accepts all elements provided by this stream.

[expand](../dart-async/stream/expand)\<S\>([Iterable](../dart-core/iterable-class)\<S\>
convert([HttpRequest](httprequest-class) element)) →
[Stream](../dart-async/stream-class)\<S\>

::: {.features}
inherited
:::

Transforms each element of this stream into a sequence of elements.

[firstWhere](../dart-async/stream/firstwhere)([bool](../dart-core/bool-class)
test([HttpRequest](httprequest-class) element),
{[HttpRequest](httprequest-class) orElse()?}) →
[Future](../dart-async/future-class)\<[HttpRequest](httprequest-class)\>

::: {.features}
inherited
:::

Finds the first element of this stream matching `test`.

[fold](../dart-async/stream/fold)\<S\>(S initialValue, S combine(S
previous, [HttpRequest](httprequest-class) element)) →
[Future](../dart-async/future-class)\<S\>

::: {.features}
inherited
:::

Combines a sequence of values by repeatedly applying `combine`.

[forEach](../dart-async/stream/foreach)(void
action([HttpRequest](httprequest-class) element)) →
[Future](../dart-async/future-class)

::: {.features}
inherited
:::

Executes `action` on each element of this stream.

[handleError](../dart-async/stream/handleerror)([Function](../dart-core/function-class)
onError, {[bool](../dart-core/bool-class) test(dynamic error)?}) →
[Stream](../dart-async/stream-class)\<[HttpRequest](httprequest-class)\>

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
test([HttpRequest](httprequest-class) element),
{[HttpRequest](httprequest-class) orElse()?}) →
[Future](../dart-async/future-class)\<[HttpRequest](httprequest-class)\>

::: {.features}
inherited
:::

Finds the last element in this stream matching `test`.

[listen](../dart-async/stream/listen)(void
onData([HttpRequest](httprequest-class) event)?,
{[Function](../dart-core/function-class)? onError, void onDone()?,
[bool](../dart-core/bool-class)? cancelOnError}) →
[StreamSubscription](../dart-async/streamsubscription-class)\<[HttpRequest](httprequest-class)\>

::: {.features}
inherited
:::

Adds a subscription to this stream.

[map](../dart-async/stream/map)\<S\>(S
convert([HttpRequest](httprequest-class) event)) →
[Stream](../dart-async/stream-class)\<S\>

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

[pipe](../dart-async/stream/pipe)([StreamConsumer](../dart-async/streamconsumer-class)\<[HttpRequest](httprequest-class)\>
streamConsumer) → [Future](../dart-async/future-class)

::: {.features}
inherited
:::

Pipes the events of this stream into `streamConsumer`.

[reduce](../dart-async/stream/reduce)([HttpRequest](httprequest-class)
combine([HttpRequest](httprequest-class) previous,
[HttpRequest](httprequest-class) element)) →
[Future](../dart-async/future-class)\<[HttpRequest](httprequest-class)\>

::: {.features}
inherited
:::

Combines a sequence of values by repeatedly applying `combine`.

[singleWhere](../dart-async/stream/singlewhere)([bool](../dart-core/bool-class)
test([HttpRequest](httprequest-class) element),
{[HttpRequest](httprequest-class) orElse()?}) →
[Future](../dart-async/future-class)\<[HttpRequest](httprequest-class)\>

::: {.features}
inherited
:::

Finds the single element in this stream matching `test`.

[skip](../dart-async/stream/skip)([int](../dart-core/int-class) count) →
[Stream](../dart-async/stream-class)\<[HttpRequest](httprequest-class)\>

::: {.features}
inherited
:::

Skips the first `count` data events from this stream.

[skipWhile](../dart-async/stream/skipwhile)([bool](../dart-core/bool-class)
test([HttpRequest](httprequest-class) element)) →
[Stream](../dart-async/stream-class)\<[HttpRequest](httprequest-class)\>

::: {.features}
inherited
:::

Skip data events from this stream while they are matched by `test`.

[take](../dart-async/stream/take)([int](../dart-core/int-class) count) →
[Stream](../dart-async/stream-class)\<[HttpRequest](httprequest-class)\>

::: {.features}
inherited
:::

Provides at most the first `count` data events of this stream.

[takeWhile](../dart-async/stream/takewhile)([bool](../dart-core/bool-class)
test([HttpRequest](httprequest-class) element)) →
[Stream](../dart-async/stream-class)\<[HttpRequest](httprequest-class)\>

::: {.features}
inherited
:::

Forwards data events while `test` is successful.

[timeout](../dart-async/stream/timeout)([Duration](../dart-core/duration-class)
timeLimit, {void
onTimeout([EventSink](../dart-async/eventsink-class)\<[HttpRequest](httprequest-class)\>
sink)?}) →
[Stream](../dart-async/stream-class)\<[HttpRequest](httprequest-class)\>

::: {.features}
inherited
:::

Creates a new stream with the same events as this stream.

[toList](../dart-async/stream/tolist)() →
[Future](../dart-async/future-class)\<[List](../dart-core/list-class)\<[HttpRequest](httprequest-class)\>\>

::: {.features}
inherited
:::

Collects all elements of this stream in a `List`.

[toSet](../dart-async/stream/toset)() →
[Future](../dart-async/future-class)\<[Set](../dart-core/set-class)\<[HttpRequest](httprequest-class)\>\>

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

[transform](../dart-async/stream/transform)\<S\>([StreamTransformer](../dart-async/streamtransformer-class)\<[HttpRequest](httprequest-class),
S\> streamTransformer) → [Stream](../dart-async/stream-class)\<S\>

::: {.features}
inherited
:::

Applies `streamTransformer` to this stream.

[where](../dart-async/stream/where)([bool](../dart-core/bool-class)
test([HttpRequest](httprequest-class) event)) →
[Stream](../dart-async/stream-class)\<[HttpRequest](httprequest-class)\>

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

Static Methods
--------------

[bind](httpserver/bind)(dynamic address, [int](../dart-core/int-class) port, {[int](../dart-core/int-class) backlog = 0, [bool](../dart-core/bool-class) v6Only = false, [bool](../dart-core/bool-class) shared = false}) → [Future](../dart-async/future-class)\<[HttpServer](httpserver-class)\>
:   Starts listening for HTTP requests on the specified `address` and
    `port`.

[bindSecure](httpserver/bindsecure)(dynamic address, [int](../dart-core/int-class) port, [SecurityContext](securitycontext-class) context, {[int](../dart-core/int-class) backlog = 0, [bool](../dart-core/bool-class) v6Only = false, [bool](../dart-core/bool-class) requestClientCertificate = false, [bool](../dart-core/bool-class) shared = false}) → [Future](../dart-async/future-class)\<[HttpServer](httpserver-class)\>
:   The `address` can either be a [String](../dart-core/string-class) or
    an [InternetAddress](internetaddress-class). If `address` is a
    [String](../dart-core/string-class), [bind](httpserver/bind) will
    perform a [InternetAddress.lookup](internetaddress/lookup) and use
    the first value in the list. To listen on the loopback adapter,
    which will allow only incoming connections from the local host, use
    the value
    [InternetAddress.loopbackIPv4](internetaddress/loopbackipv4) or
    [InternetAddress.loopbackIPv6](internetaddress/loopbackipv6). To
    allow for incoming connection from the network use either one of the
    values [InternetAddress.anyIPv4](internetaddress/anyipv4) or
    [InternetAddress.anyIPv6](internetaddress/anyipv6) to bind to all
    interfaces or the IP address of a specific interface.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpServer-class.html>
:::
