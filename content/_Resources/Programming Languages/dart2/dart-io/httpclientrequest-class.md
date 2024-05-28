[dart:io](../dart-io/dart-io-library){._links-link}

HttpClientRequest class
=======================

HTTP request for a client connection.

To set up a request, set the headers using the headers property provided
in this class and write the data to the body of the request.
`HttpClientRequest` is an [IOSink](iosink-class). Use the methods from
IOSink, such as `writeCharCode()`, to write the body of the HTTP
request. When one of the IOSink methods is used for the first time, the
request header is sent. Calling any methods that change the header after
it is sent throws an exception.

When writing string data through the [IOSink](iosink-class) the encoding
used is determined from the \"charset\" parameter of the
\"Content-Type\" header.

``` {.language-dart data-language="dart"}
var client = HttpClient();
HttpClientRequest request = await client.get('localhost', 80, '/file.txt');
request.headers.contentType =
    ContentType('application', 'json', charset: 'utf-8');
request.write('text content👍🎯'); // Strings written will be UTF-8 encoded.
```

If no charset is provided the default of ISO-8859-1 (Latin 1) is used.

``` {.language-dart data-language="dart"}
var client = HttpClient();
HttpClientRequest request = await client.get('localhost', 80, '/file.txt');
request.headers.add(HttpHeaders.contentTypeHeader, "text/plain");
request.write('blåbærgrød'); // Strings written will be ISO-8859-1 encoded
```

An exception is thrown if you use an unsupported encoding and the
`write()` method being used takes a string parameter.

Implemented types

:   -   [IOSink](iosink-class)

Constructors
------------

[HttpClientRequest](httpclientrequest/httpclientrequest)()

Properties {#instance-properties}
----------

[bufferOutput](httpclientrequest/bufferoutput) ↔
[bool](../dart-core/bool-class)

::: {.features}
read / write
:::

Gets or sets if the [HttpClientRequest](httpclientrequest-class) should
buffer output.

[connectionInfo](httpclientrequest/connectioninfo) →
[HttpConnectionInfo](httpconnectioninfo-class)?

::: {.features}
read-only
:::

Gets information about the client connection.

[contentLength](httpclientrequest/contentlength) ↔
[int](../dart-core/int-class)

::: {.features}
read / write
:::

Gets and sets the content length of the request.

[cookies](httpclientrequest/cookies) →
[List](../dart-core/list-class)\<[Cookie](cookie-class)\>

::: {.features}
read-only
:::

Cookies to present to the server (in the \'cookie\' header).

[done](httpclientrequest/done) →
[Future](../dart-async/future-class)\<[HttpClientResponse](httpclientresponse-class)\>

::: {.features}
read-only, override
:::

A `HttpClientResponse` future that will complete once the response is
available.

[encoding](iosink/encoding) ↔ [Encoding](../dart-convert/encoding-class)

::: {.features}
read / write, inherited
:::

The [Encoding](../dart-convert/encoding-class) used when writing
strings.

[followRedirects](httpclientrequest/followredirects) ↔
[bool](../dart-core/bool-class)

::: {.features}
read / write
:::

Whether to follow redirects automatically.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[headers](httpclientrequest/headers) → [HttpHeaders](httpheaders-class)

::: {.features}
read-only
:::

Returns the client request headers.

[maxRedirects](httpclientrequest/maxredirects) ↔
[int](../dart-core/int-class)

::: {.features}
read / write
:::

Set this property to the maximum number of redirects to follow when
[followRedirects](httpclientrequest/followredirects) is `true`. If this
number is exceeded an error event will be added with a
[RedirectException](redirectexception-class).

[method](httpclientrequest/method) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

The method of the request.

[persistentConnection](httpclientrequest/persistentconnection) ↔
[bool](../dart-core/bool-class)

::: {.features}
read / write
:::

The requested persistent connection state.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[uri](httpclientrequest/uri) → [Uri](../dart-core/uri-class)

::: {.features}
read-only
:::

The uri of the request.

Methods {#instance-methods}
-------

[abort](httpclientrequest/abort)(\[[Object](../dart-core/object-class)?
exception, [StackTrace](../dart-core/stacktrace-class)? stackTrace\]) →
void

::: {.features}
\@Since(\"2.10\")
:::

Aborts the client connection.

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

[close](httpclientrequest/close)() →
[Future](../dart-async/future-class)\<[HttpClientResponse](httpclientresponse-class)\>

::: {.features}
override
:::

Close the request for input. Returns the value of
[done](httpclientrequest/done).

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
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClientRequest-class.html>
:::
