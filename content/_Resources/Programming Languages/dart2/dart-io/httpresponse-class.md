[dart:io](../dart-io/dart-io-library){._links-link}

HttpResponse class
==================

An HTTP response, which returns the headers and data from the server to
the client in response to an HTTP request.

Every HttpRequest object provides access to the associated
[HttpResponse](httpresponse-class) object through the `response`
property. The server sends its response to the client by writing to the
HttpResponse object.

Writing the response
--------------------

This class implements [IOSink](iosink-class). After the header has been
set up, the methods from IOSink, such as `writeln()`, can be used to
write the body of the HTTP response. Use the `close()` method to close
the response and send it to the client.

``` {.language-dart data-language="dart"}
server.listen((HttpRequest request) {
  request.response.write('Hello, world!');
  request.response.close();
});
```

When one of the IOSink methods is used for the first time, the request
header is sent. Calling any methods that change the header after it is
sent throws an exception.

Setting the headers
-------------------

The HttpResponse object has a number of properties for setting up the
HTTP headers of the response. When writing string data through the
IOSink, the encoding used is determined from the \"charset\" parameter
of the \"Content-Type\" header.

``` {.language-dart data-language="dart"}
HttpResponse response = ...
response.headers.contentType
    = ContentType("application", "json", charset: "utf-8");
response.write(...);  // Strings written will be UTF-8 encoded.
```

If no charset is provided the default of ISO-8859-1 (Latin 1) will be
used.

``` {.language-dart data-language="dart"}
HttpResponse response = ...
response.headers.add(HttpHeaders.contentTypeHeader, "text/plain");
response.write(...);  // Strings written will be ISO-8859-1 encoded.
```

An exception is thrown if you use the `write()` method while an
unsupported content-type is set.

Implemented types

:   -   [IOSink](iosink-class)

Constructors
------------

[HttpResponse](httpresponse/httpresponse)()

Properties {#instance-properties}
----------

[bufferOutput](httpresponse/bufferoutput) ↔
[bool](../dart-core/bool-class)

::: {.features}
read / write
:::

Gets or sets if the [HttpResponse](httpresponse-class) should buffer
output.

[connectionInfo](httpresponse/connectioninfo) →
[HttpConnectionInfo](httpconnectioninfo-class)?

::: {.features}
read-only
:::

Gets information about the client connection. Returns `null` if the
socket is not available.

[contentLength](httpresponse/contentlength) ↔
[int](../dart-core/int-class)

::: {.features}
read / write
:::

Gets and sets the content length of the response. If the size of the
response is not known in advance set the content length to -1, which is
also the default if not set.

[cookies](httpresponse/cookies) →
[List](../dart-core/list-class)\<[Cookie](cookie-class)\>

::: {.features}
read-only
:::

Cookies to set in the client (in the \'set-cookie\' header).

[deadline](httpresponse/deadline) ↔
[Duration](../dart-core/duration-class)?

::: {.features}
read / write
:::

Set and get the [deadline](httpresponse/deadline) for the response. The
deadline is timed from the time it\'s set. Setting a new deadline will
override any previous deadline. When a deadline is exceeded, the
response will be closed and any further data ignored.

[done](iosink/done) → [Future](../dart-async/future-class)

::: {.features}
read-only, inherited
:::

A future that will complete when the consumer closes, or when an error
occurs.

[encoding](iosink/encoding) ↔ [Encoding](../dart-convert/encoding-class)

::: {.features}
read / write, inherited
:::

The [Encoding](../dart-convert/encoding-class) used when writing
strings.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[headers](httpresponse/headers) → [HttpHeaders](httpheaders-class)

::: {.features}
read-only
:::

Returns the response headers.

[persistentConnection](httpresponse/persistentconnection) ↔
[bool](../dart-core/bool-class)

::: {.features}
read / write
:::

Gets and sets the persistent connection state. The initial value of this
property is the persistent connection state from the request.

[reasonPhrase](httpresponse/reasonphrase) ↔
[String](../dart-core/string-class)

::: {.features}
read / write
:::

The reason phrase for the response.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[statusCode](httpresponse/statuscode) ↔ [int](../dart-core/int-class)

::: {.features}
read / write
:::

The status code of the response.

Methods {#instance-methods}
-------

[add](iosink/add)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
data) → void

::: {.features}
inherited
:::

Adds byte `data` to the target consumer, ignoring
[encoding](iosink/encoding).

[addError](iosink/adderror)([Object](../dart-core/object-class) error,
\[[StackTrace](../dart-core/stacktrace-class)? stackTrace\]) → void

::: {.features}
inherited
:::

Passes the error to the target consumer as an error event.

[addStream](iosink/addstream)([Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
stream) → [Future](../dart-async/future-class)

::: {.features}
inherited
:::

Adds all elements of the given `stream`.

[close](iosink/close)() → [Future](../dart-async/future-class)

::: {.features}
inherited
:::

Close the target consumer.

[detachSocket](httpresponse/detachsocket)({[bool](../dart-core/bool-class)
writeHeaders = true}) →
[Future](../dart-async/future-class)\<[Socket](socket-class)\>

Detaches the underlying socket from the HTTP server. When the socket is
detached the HTTP server will no longer perform any operations on it.

[flush](iosink/flush)() → [Future](../dart-async/future-class)

::: {.features}
inherited
:::

Returns a [Future](../dart-async/future-class) that completes once all
buffered data is accepted by the underlying
[StreamConsumer](../dart-async/streamconsumer-class).

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[redirect](httpresponse/redirect)([Uri](../dart-core/uri-class)
location, {[int](../dart-core/int-class) status =
HttpStatus.movedTemporarily}) → [Future](../dart-async/future-class)

Respond with a redirect to `location`.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[write](iosink/write)([Object](../dart-core/object-class)? object) →
void

::: {.features}
inherited
:::

Converts `object` to a String by invoking
[Object.toString](../dart-core/object/tostring) and [add](iosink/add)s
the encoding of the result to the target consumer.

[writeAll](iosink/writeall)([Iterable](../dart-core/iterable-class)
objects, \[[String](../dart-core/string-class) separator = \"\"\]) →
void

::: {.features}
inherited
:::

Iterates over the given `objects` and [write](iosink/write)s them in
sequence.

[writeCharCode](iosink/writecharcode)([int](../dart-core/int-class)
charCode) → void

::: {.features}
inherited
:::

Writes the character of `charCode`.

[writeln](iosink/writeln)(\[[Object](../dart-core/object-class)? object
= \"\"\]) → void

::: {.features}
inherited
:::

Converts `object` to a String by invoking
[Object.toString](../dart-core/object/tostring) and writes the result to
`this`, followed by a newline.

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
<https://api.dart.dev/stable/2.18.5/dart-io/HttpResponse-class.html>
:::
