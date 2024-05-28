[dart:io](../dart-io/dart-io-library){._links-link}

HttpClient class
================

An HTTP client for communicating with an HTTP server.

Sends HTTP requests to an HTTP server and receives responses. Maintains
state, including session cookies and other cookies, between multiple
requests to the same server.

Note: [HttpClient](httpclient-class) provides low-level HTTP
functionality. We recommend users start with more developer-friendly and
composable APIs found in
[`package:http`](https://pub.dev/packages/http).

HttpClient contains a number of methods to send an
[HttpClientRequest](httpclientrequest-class) to an Http server and
receive an [HttpClientResponse](httpclientresponse-class) back. For
example, you can use the [get](httpclient/get),
[getUrl](httpclient/geturl), [post](httpclient/post), and
[postUrl](httpclient/posturl) methods for GET and POST requests,
respectively.

Making a simple GET request: an example
---------------------------------------

A `getUrl` request is a two-step process, triggered by two
[Future](../dart-async/future-class)s. When the first future completes
with a [HttpClientRequest](httpclientrequest-class), the underlying
network connection has been established, but no data has been sent. In
the callback function for the first future, the HTTP headers and body
can be set on the request. Either the first write to the request object
or a call to [close](httpclient/close) sends the request to the server.

When the HTTP response is received from the server, the second future,
which is returned by close, completes with an
[HttpClientResponse](httpclientresponse-class) object. This object
provides access to the headers and body of the response. The body is
available as a stream implemented by `HttpClientResponse`. If a body is
present, it must be read. Otherwise, it leads to resource leaks.
Consider using [HttpClientResponse.drain](../dart-async/stream/drain) if
the body is unused.

``` {.language-dart data-language="dart"}
var client = HttpClient();
try {
  HttpClientRequest request = await client.get('localhost', 80, '/file.txt');
  // Optionally set up headers...
  // Optionally write to the request object...
  HttpClientResponse response = await request.close();
  // Process the response
  final stringData = await response.transform(utf8.decoder).join();
  print(stringData);
} finally {
  client.close();
}
```

The future for [HttpClientRequest](httpclientrequest-class) is created
by methods such as [getUrl](httpclient/geturl) and
[open](httpclient/open).

HTTPS connections
-----------------

An `HttpClient` can make HTTPS requests, connecting to a server using
the TLS (SSL) secure networking protocol. Calling
[getUrl](httpclient/geturl) with an https: scheme will work
automatically, if the server\'s certificate is signed by a root CA
(certificate authority) on the default list of well-known trusted CAs,
compiled by Mozilla.

To add a custom trusted certificate authority, or to send a client
certificate to servers that request one, pass a
[SecurityContext](securitycontext-class) object as the optional
`context` argument to the `HttpClient` constructor. The desired security
options can be set on the [SecurityContext](securitycontext-class)
object.

Headers
-------

All `HttpClient` requests set the following header by default:

``` {.language-dart data-language="dart"}
Accept-Encoding: gzip
```

This allows the HTTP server to use gzip compression for the body if
possible. If this behavior is not desired set the `Accept-Encoding`
header to something else. To turn off gzip compression of the response,
clear this header:

``` {.language-dart data-language="dart"}
request.headers.removeAll(HttpHeaders.acceptEncodingHeader)
```

Closing the `HttpClient`
------------------------

`HttpClient` supports persistent connections and caches network
connections to reuse them for multiple requests whenever possible. This
means that network connections can be kept open for some time after a
request has completed. Use [HttpClient.close](httpclient/close) to force
the `HttpClient` object to shut down and to close the idle network
connections.

Turning proxies on and off
--------------------------

By default the `HttpClient` uses the proxy configuration available from
the environment, see
[findProxyFromEnvironment](httpclient/findproxyfromenvironment). To turn
off the use of proxies set the [findProxy](httpclient/findproxy)
property to `null`.

``` {.language-dart data-language="dart"}
HttpClient client = HttpClient();
client.findProxy = null;
```

Constructors
------------

[HttpClient](httpclient/httpclient)({[SecurityContext](securitycontext-class)?
context})

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[authenticate](httpclient/authenticate) ←
([Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>
Function?([Uri](../dart-core/uri-class) url,
[String](../dart-core/string-class) scheme,
[String](../dart-core/string-class)? realm)?)

::: {.features}
write-only
:::

Sets the function to be called when a site is requesting authentication.

[authenticateProxy](httpclient/authenticateproxy) ←
([Future](../dart-async/future-class)\<[bool](../dart-core/bool-class)\>
Function?([String](../dart-core/string-class) host,
[int](../dart-core/int-class) port, [String](../dart-core/string-class)
scheme, [String](../dart-core/string-class)? realm)?)

::: {.features}
write-only
:::

Sets the function to be called when a proxy is requesting
authentication.

[autoUncompress](httpclient/autouncompress) ↔
[bool](../dart-core/bool-class)

::: {.features}
read / write
:::

Gets and sets whether the body of a response will be automatically
uncompressed.

[badCertificateCallback](httpclient/badcertificatecallback) ←
([bool](../dart-core/bool-class)
Function?([X509Certificate](x509certificate-class) cert,
[String](../dart-core/string-class) host, [int](../dart-core/int-class)
port)?)

::: {.features}
write-only
:::

Sets a callback that will decide whether to accept a secure connection
with a server certificate that cannot be authenticated by any of our
trusted root certificates.

[connectionFactory](httpclient/connectionfactory) ←
([Future](../dart-async/future-class)\<[ConnectionTask](connectiontask-class)\<[Socket](socket-class)\>\>
Function?([Uri](../dart-core/uri-class) url,
[String](../dart-core/string-class)? proxyHost,
[int](../dart-core/int-class)? proxyPort)?)

::: {.features}
write-only
:::

Sets the function used to create socket connections.

[connectionTimeout](httpclient/connectiontimeout) ↔
[Duration](../dart-core/duration-class)?

::: {.features}
read / write
:::

Gets and sets the connection timeout.

[findProxy](httpclient/findproxy) ← ([String](../dart-core/string-class)
Function?([Uri](../dart-core/uri-class) url)?)

::: {.features}
write-only
:::

Sets the function used to resolve the proxy server to be used for
opening a HTTP connection to the specified `url`. If this function is
not set, direct connections will always be used.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[idleTimeout](httpclient/idletimeout) ↔
[Duration](../dart-core/duration-class)

::: {.features}
read / write
:::

Gets and sets the idle timeout of non-active persistent (keep-alive)
connections.

[keyLog](httpclient/keylog) ← (dynamic
Function?([String](../dart-core/string-class) line)?)

::: {.features}
write-only
:::

Sets a callback that will be called when new TLS keys are exchanged with
the server. It will receive one line of text in [NSS Key Log
Format](https://developer.mozilla.org/en-US/docs/Mozilla/Projects/NSS/Key_Log_Format)
for each call. Writing these lines to a file will allow tools (such as
[Wireshark](https://gitlab.com/wireshark/wireshark/-/wikis/TLS#tls-decryption))
to decrypt communication between the this client and the server. This is
meant to allow network-level debugging of secure sockets and should not
be used in production code. For example:

[maxConnectionsPerHost](httpclient/maxconnectionsperhost) ↔
[int](../dart-core/int-class)?

::: {.features}
read / write
:::

Gets and sets the maximum number of live connections, to a single host.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[userAgent](httpclient/useragent) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

Gets and sets the default value of the `User-Agent` header for all
requests generated by this [HttpClient](httpclient-class).

Methods {#instance-methods}
-------

[addCredentials](httpclient/addcredentials)([Uri](../dart-core/uri-class)
url, [String](../dart-core/string-class) realm,
[HttpClientCredentials](httpclientcredentials-class) credentials) → void

Add credentials to be used for authorizing HTTP requests.

[addProxyCredentials](httpclient/addproxycredentials)([String](../dart-core/string-class)
host, [int](../dart-core/int-class) port,
[String](../dart-core/string-class) realm,
[HttpClientCredentials](httpclientcredentials-class) credentials) → void

Add credentials to be used for authorizing HTTP proxies.

[close](httpclient/close)({[bool](../dart-core/bool-class) force =
false}) → void

Shuts down the HTTP client.

[delete](httpclient/delete)([String](../dart-core/string-class) host,
[int](../dart-core/int-class) port, [String](../dart-core/string-class)
path) →
[Future](../dart-async/future-class)\<[HttpClientRequest](httpclientrequest-class)\>

Opens a HTTP connection using the DELETE method.

[deleteUrl](httpclient/deleteurl)([Uri](../dart-core/uri-class) url) →
[Future](../dart-async/future-class)\<[HttpClientRequest](httpclientrequest-class)\>

Opens a HTTP connection using the DELETE method.

[get](httpclient/get)([String](../dart-core/string-class) host,
[int](../dart-core/int-class) port, [String](../dart-core/string-class)
path) →
[Future](../dart-async/future-class)\<[HttpClientRequest](httpclientrequest-class)\>

Opens a HTTP connection using the GET method.

[getUrl](httpclient/geturl)([Uri](../dart-core/uri-class) url) →
[Future](../dart-async/future-class)\<[HttpClientRequest](httpclientrequest-class)\>

Opens a HTTP connection using the GET method.

[head](httpclient/head)([String](../dart-core/string-class) host,
[int](../dart-core/int-class) port, [String](../dart-core/string-class)
path) →
[Future](../dart-async/future-class)\<[HttpClientRequest](httpclientrequest-class)\>

Opens a HTTP connection using the HEAD method.

[headUrl](httpclient/headurl)([Uri](../dart-core/uri-class) url) →
[Future](../dart-async/future-class)\<[HttpClientRequest](httpclientrequest-class)\>

Opens a HTTP connection using the HEAD method.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[open](httpclient/open)([String](../dart-core/string-class) method,
[String](../dart-core/string-class) host, [int](../dart-core/int-class)
port, [String](../dart-core/string-class) path) →
[Future](../dart-async/future-class)\<[HttpClientRequest](httpclientrequest-class)\>

Opens a HTTP connection.

[openUrl](httpclient/openurl)([String](../dart-core/string-class)
method, [Uri](../dart-core/uri-class) url) →
[Future](../dart-async/future-class)\<[HttpClientRequest](httpclientrequest-class)\>

Opens a HTTP connection.

[patch](httpclient/patch)([String](../dart-core/string-class) host,
[int](../dart-core/int-class) port, [String](../dart-core/string-class)
path) →
[Future](../dart-async/future-class)\<[HttpClientRequest](httpclientrequest-class)\>

Opens a HTTP connection using the PATCH method.

[patchUrl](httpclient/patchurl)([Uri](../dart-core/uri-class) url) →
[Future](../dart-async/future-class)\<[HttpClientRequest](httpclientrequest-class)\>

Opens a HTTP connection using the PATCH method.

[post](httpclient/post)([String](../dart-core/string-class) host,
[int](../dart-core/int-class) port, [String](../dart-core/string-class)
path) →
[Future](../dart-async/future-class)\<[HttpClientRequest](httpclientrequest-class)\>

Opens a HTTP connection using the POST method.

[postUrl](httpclient/posturl)([Uri](../dart-core/uri-class) url) →
[Future](../dart-async/future-class)\<[HttpClientRequest](httpclientrequest-class)\>

Opens a HTTP connection using the POST method.

[put](httpclient/put)([String](../dart-core/string-class) host,
[int](../dart-core/int-class) port, [String](../dart-core/string-class)
path) →
[Future](../dart-async/future-class)\<[HttpClientRequest](httpclientrequest-class)\>

Opens a HTTP connection using the PUT method.

[putUrl](httpclient/puturl)([Uri](../dart-core/uri-class) url) →
[Future](../dart-async/future-class)\<[HttpClientRequest](httpclientrequest-class)\>

Opens a HTTP connection using the PUT method.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

Static Properties
-----------------

[enableTimelineLogging](httpclient/enabletimelinelogging) ↔
[bool](../dart-core/bool-class)

::: {.features}
read / write
:::

Current state of HTTP request logging from all
[HttpClient](httpclient-class)s to the developer timeline.

Static Methods
--------------

[findProxyFromEnvironment](httpclient/findproxyfromenvironment)([Uri](../dart-core/uri-class) url, {[Map](../dart-core/map-class)\<[String](../dart-core/string-class), [String](../dart-core/string-class)\>? environment}) → [String](../dart-core/string-class)
:   Function for resolving the proxy server to be used for a HTTP
    connection from the proxy configuration specified through
    environment variables.

Constants
---------

[defaultHttpPort](httpclient/defaulthttpport-constant) → const [int](../dart-core/int-class)

:   <div>

    `80`

    </div>

[defaultHttpsPort](httpclient/defaulthttpsport-constant) → const [int](../dart-core/int-class)

:   <div>

    `443`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClient-class.html>
:::
