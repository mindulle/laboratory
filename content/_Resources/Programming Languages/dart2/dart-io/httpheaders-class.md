[dart:io](../dart-io/dart-io-library){._links-link}

HttpHeaders class
=================

Headers for HTTP requests and responses.

In some situations, headers are immutable:

-   [HttpRequest](httprequest-class) and
    [HttpClientResponse](httpclientresponse-class) always have immutable
    headers.

-   [HttpResponse](httpresponse-class) and
    [HttpClientRequest](httpclientrequest-class) have immutable headers
    from the moment the body is written to.

In these situations, the mutating methods throw exceptions.

For all operations on HTTP headers the header name is case-insensitive.

To set the value of a header use the `set()` method:

``` {.language-dart data-language="dart"}
request.headers.set(HttpHeaders.cacheControlHeader,
                    'max-age=3600, must-revalidate');
```

To retrieve the value of a header use the `value()` method:

``` {.language-dart data-language="dart"}
print(request.headers.value(HttpHeaders.userAgentHeader));
```

An `HttpHeaders` object holds a list of values for each name as the
standard allows. In most cases a name holds only a single value, The
most common mode of operation is to use `set()` for setting a value, and
`value()` for retrieving a value.

Constructors
------------

[HttpHeaders](httpheaders/httpheaders)()

Properties {#instance-properties}
----------

[chunkedTransferEncoding](httpheaders/chunkedtransferencoding) ↔
[bool](../dart-core/bool-class)

::: {.features}
read / write
:::

Whether the connection uses chunked transfer encoding.

[contentLength](httpheaders/contentlength) ↔
[int](../dart-core/int-class)

::: {.features}
read / write
:::

The value of the
[contentLengthHeader](httpheaders/contentlengthheader-constant) header,
if any.

[contentType](httpheaders/contenttype) ↔
[ContentType](contenttype-class)?

::: {.features}
read / write
:::

The [ContentType](contenttype-class) of the
[contentTypeHeader](httpheaders/contenttypeheader-constant) header, if
any.

[date](httpheaders/date) ↔ [DateTime](../dart-core/datetime-class)?

::: {.features}
read / write
:::

The date specified by the [dateHeader](httpheaders/dateheader-constant)
header, if any.

[expires](httpheaders/expires) ↔
[DateTime](../dart-core/datetime-class)?

::: {.features}
read / write
:::

The date and time specified by the
[expiresHeader](httpheaders/expiresheader-constant) header, if any.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[host](httpheaders/host) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

The value of the [hostHeader](httpheaders/hostheader-constant) header,
if any.

[ifModifiedSince](httpheaders/ifmodifiedsince) ↔
[DateTime](../dart-core/datetime-class)?

::: {.features}
read / write
:::

The date and time specified by the
[ifModifiedSinceHeader](httpheaders/ifmodifiedsinceheader-constant)
header, if any.

[persistentConnection](httpheaders/persistentconnection) ↔
[bool](../dart-core/bool-class)

::: {.features}
read / write
:::

Whether the connection is persistent (keep-alive).

[port](httpheaders/port) ↔ [int](../dart-core/int-class)?

::: {.features}
read / write
:::

The value of the port part of the
[hostHeader](httpheaders/hostheader-constant) header, if any.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[add](httpheaders/add)([String](../dart-core/string-class) name,
[Object](../dart-core/object-class) value,
{[bool](../dart-core/bool-class) preserveHeaderCase = false}) → void

Adds a header value.

[clear](httpheaders/clear)() → void

Removes all headers.

[forEach](httpheaders/foreach)(void
action([String](../dart-core/string-class) name,
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>
values)) → void

Performs the `action` on each header.

[noFolding](httpheaders/nofolding)([String](../dart-core/string-class)
name) → void

Disables folding for the header named `name` when sending the HTTP
header.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[remove](httpheaders/remove)([String](../dart-core/string-class) name,
[Object](../dart-core/object-class) value) → void

Removes a specific value for a header name.

[removeAll](httpheaders/removeall)([String](../dart-core/string-class)
name) → void

Removes all values for the specified header name.

[set](httpheaders/set)([String](../dart-core/string-class) name,
[Object](../dart-core/object-class) value,
{[bool](../dart-core/bool-class) preserveHeaderCase = false}) → void

Sets the header `name` to `value`.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[value](httpheaders/value)([String](../dart-core/string-class) name) →
[String](../dart-core/string-class)?

Convenience method for the value for a single valued header.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

[operator
\[\]](httpheaders/operator_get)([String](../dart-core/string-class)
name) →
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>?

The values for the header named `name`.

Constants
---------

[acceptCharsetHeader](httpheaders/acceptcharsetheader-constant) → const
[String](../dart-core/string-class)

<div>

`"accept-charset"`

</div>

[acceptEncodingHeader](httpheaders/acceptencodingheader-constant) →
const [String](../dart-core/string-class)

<div>

`"accept-encoding"`

</div>

[acceptHeader](httpheaders/acceptheader-constant) → const
[String](../dart-core/string-class)

<div>

`"accept"`

</div>

[acceptLanguageHeader](httpheaders/acceptlanguageheader-constant) →
const [String](../dart-core/string-class)

<div>

`"accept-language"`

</div>

[acceptRangesHeader](httpheaders/acceptrangesheader-constant) → const
[String](../dart-core/string-class)

<div>

`"accept-ranges"`

</div>

[accessControlAllowCredentialsHeader](httpheaders/accesscontrolallowcredentialsheader-constant)
→ const [String](../dart-core/string-class)

::: {.features}
\@Since(\"2.14\")
:::

<div>

`'access-control-allow-credentials'`

</div>

[accessControlAllowHeadersHeader](httpheaders/accesscontrolallowheadersheader-constant)
→ const [String](../dart-core/string-class)

::: {.features}
\@Since(\"2.14\")
:::

<div>

`'access-control-allow-headers'`

</div>

[accessControlAllowMethodsHeader](httpheaders/accesscontrolallowmethodsheader-constant)
→ const [String](../dart-core/string-class)

::: {.features}
\@Since(\"2.14\")
:::

<div>

`'access-control-allow-methods'`

</div>

[accessControlAllowOriginHeader](httpheaders/accesscontrolalloworiginheader-constant)
→ const [String](../dart-core/string-class)

::: {.features}
\@Since(\"2.14\")
:::

<div>

`'access-control-allow-origin'`

</div>

[accessControlExposeHeadersHeader](httpheaders/accesscontrolexposeheadersheader-constant)
→ const [String](../dart-core/string-class)

::: {.features}
\@Since(\"2.14\")
:::

<div>

`'access-control-expose-headers'`

</div>

[accessControlMaxAgeHeader](httpheaders/accesscontrolmaxageheader-constant)
→ const [String](../dart-core/string-class)

::: {.features}
\@Since(\"2.14\")
:::

<div>

`'access-control-max-age'`

</div>

[accessControlRequestHeadersHeader](httpheaders/accesscontrolrequestheadersheader-constant)
→ const [String](../dart-core/string-class)

::: {.features}
\@Since(\"2.14\")
:::

<div>

`'access-control-request-headers'`

</div>

[accessControlRequestMethodHeader](httpheaders/accesscontrolrequestmethodheader-constant)
→ const [String](../dart-core/string-class)

::: {.features}
\@Since(\"2.14\")
:::

<div>

`'access-control-request-method'`

</div>

[ageHeader](httpheaders/ageheader-constant) → const
[String](../dart-core/string-class)

<div>

`"age"`

</div>

[allowHeader](httpheaders/allowheader-constant) → const
[String](../dart-core/string-class)

<div>

`"allow"`

</div>

[authorizationHeader](httpheaders/authorizationheader-constant) → const
[String](../dart-core/string-class)

<div>

`"authorization"`

</div>

[cacheControlHeader](httpheaders/cachecontrolheader-constant) → const
[String](../dart-core/string-class)

<div>

`"cache-control"`

</div>

[connectionHeader](httpheaders/connectionheader-constant) → const
[String](../dart-core/string-class)

<div>

`"connection"`

</div>

[contentEncodingHeader](httpheaders/contentencodingheader-constant) →
const [String](../dart-core/string-class)

<div>

`"content-encoding"`

</div>

[contentLanguageHeader](httpheaders/contentlanguageheader-constant) →
const [String](../dart-core/string-class)

<div>

`"content-language"`

</div>

[contentLengthHeader](httpheaders/contentlengthheader-constant) → const
[String](../dart-core/string-class)

<div>

`"content-length"`

</div>

[contentLocationHeader](httpheaders/contentlocationheader-constant) →
const [String](../dart-core/string-class)

<div>

`"content-location"`

</div>

[contentMD5Header](httpheaders/contentmd5header-constant) → const
[String](../dart-core/string-class)

<div>

`"content-md5"`

</div>

[contentRangeHeader](httpheaders/contentrangeheader-constant) → const
[String](../dart-core/string-class)

<div>

`"content-range"`

</div>

[contentTypeHeader](httpheaders/contenttypeheader-constant) → const
[String](../dart-core/string-class)

<div>

`"content-type"`

</div>

[cookieHeader](httpheaders/cookieheader-constant) → const
[String](../dart-core/string-class)

<div>

`"cookie"`

</div>

[dateHeader](httpheaders/dateheader-constant) → const
[String](../dart-core/string-class)

<div>

`"date"`

</div>

[entityHeaders](httpheaders/entityheaders-constant) → const
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>

<div>

`[allowHeader, contentEncodingHeader, contentLanguageHeader, contentLengthHeader, contentLocationHeader, contentMD5Header, contentRangeHeader, contentTypeHeader, expiresHeader, lastModifiedHeader]`

</div>

[etagHeader](httpheaders/etagheader-constant) → const
[String](../dart-core/string-class)

<div>

`"etag"`

</div>

[expectHeader](httpheaders/expectheader-constant) → const
[String](../dart-core/string-class)

<div>

`"expect"`

</div>

[expiresHeader](httpheaders/expiresheader-constant) → const
[String](../dart-core/string-class)

<div>

`"expires"`

</div>

[fromHeader](httpheaders/fromheader-constant) → const
[String](../dart-core/string-class)

<div>

`"from"`

</div>

[generalHeaders](httpheaders/generalheaders-constant) → const
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>

<div>

`[cacheControlHeader, connectionHeader, dateHeader, pragmaHeader, trailerHeader, transferEncodingHeader, upgradeHeader, viaHeader, warningHeader]`

</div>

[hostHeader](httpheaders/hostheader-constant) → const
[String](../dart-core/string-class)

<div>

`"host"`

</div>

[ifMatchHeader](httpheaders/ifmatchheader-constant) → const
[String](../dart-core/string-class)

<div>

`"if-match"`

</div>

[ifModifiedSinceHeader](httpheaders/ifmodifiedsinceheader-constant) →
const [String](../dart-core/string-class)

<div>

`"if-modified-since"`

</div>

[ifNoneMatchHeader](httpheaders/ifnonematchheader-constant) → const
[String](../dart-core/string-class)

<div>

`"if-none-match"`

</div>

[ifRangeHeader](httpheaders/ifrangeheader-constant) → const
[String](../dart-core/string-class)

<div>

`"if-range"`

</div>

[ifUnmodifiedSinceHeader](httpheaders/ifunmodifiedsinceheader-constant)
→ const [String](../dart-core/string-class)

<div>

`"if-unmodified-since"`

</div>

[lastModifiedHeader](httpheaders/lastmodifiedheader-constant) → const
[String](../dart-core/string-class)

<div>

`"last-modified"`

</div>

[locationHeader](httpheaders/locationheader-constant) → const
[String](../dart-core/string-class)

<div>

`"location"`

</div>

[maxForwardsHeader](httpheaders/maxforwardsheader-constant) → const
[String](../dart-core/string-class)

<div>

`"max-forwards"`

</div>

[pragmaHeader](httpheaders/pragmaheader-constant) → const
[String](../dart-core/string-class)

<div>

`"pragma"`

</div>

[proxyAuthenticateHeader](httpheaders/proxyauthenticateheader-constant)
→ const [String](../dart-core/string-class)

<div>

`"proxy-authenticate"`

</div>

[proxyAuthorizationHeader](httpheaders/proxyauthorizationheader-constant)
→ const [String](../dart-core/string-class)

<div>

`"proxy-authorization"`

</div>

[rangeHeader](httpheaders/rangeheader-constant) → const
[String](../dart-core/string-class)

<div>

`"range"`

</div>

[refererHeader](httpheaders/refererheader-constant) → const
[String](../dart-core/string-class)

<div>

`"referer"`

</div>

[requestHeaders](httpheaders/requestheaders-constant) → const
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>

<div>

`[acceptHeader, acceptCharsetHeader, acceptEncodingHeader, acceptLanguageHeader, authorizationHeader, expectHeader, fromHeader, hostHeader, ifMatchHeader, ifModifiedSinceHeader, ifNoneMatchHeader, ifRa…`

</div>

[responseHeaders](httpheaders/responseheaders-constant) → const
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>

<div>

`[acceptRangesHeader, ageHeader, etagHeader, locationHeader, proxyAuthenticateHeader, retryAfterHeader, serverHeader, varyHeader, wwwAuthenticateHeader]`

</div>

[retryAfterHeader](httpheaders/retryafterheader-constant) → const
[String](../dart-core/string-class)

<div>

`"retry-after"`

</div>

[serverHeader](httpheaders/serverheader-constant) → const
[String](../dart-core/string-class)

<div>

`"server"`

</div>

[setCookieHeader](httpheaders/setcookieheader-constant) → const
[String](../dart-core/string-class)

<div>

`"set-cookie"`

</div>

[teHeader](httpheaders/teheader-constant) → const
[String](../dart-core/string-class)

<div>

`"te"`

</div>

[trailerHeader](httpheaders/trailerheader-constant) → const
[String](../dart-core/string-class)

<div>

`"trailer"`

</div>

[transferEncodingHeader](httpheaders/transferencodingheader-constant) →
const [String](../dart-core/string-class)

<div>

`"transfer-encoding"`

</div>

[upgradeHeader](httpheaders/upgradeheader-constant) → const
[String](../dart-core/string-class)

<div>

`"upgrade"`

</div>

[userAgentHeader](httpheaders/useragentheader-constant) → const
[String](../dart-core/string-class)

<div>

`"user-agent"`

</div>

[varyHeader](httpheaders/varyheader-constant) → const
[String](../dart-core/string-class)

<div>

`"vary"`

</div>

[viaHeader](httpheaders/viaheader-constant) → const
[String](../dart-core/string-class)

<div>

`"via"`

</div>

[warningHeader](httpheaders/warningheader-constant) → const
[String](../dart-core/string-class)

<div>

`"warning"`

</div>

[wwwAuthenticateHeader](httpheaders/wwwauthenticateheader-constant) →
const [String](../dart-core/string-class)

<div>

`"www-authenticate"`

</div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpHeaders-class.html>
:::
