[dart:core](../dart-core/dart-core-library){._links-link}

Uri class
=========

A parsed URI, such as a URL.

To create a URI with specific components, use [new Uri](uri/uri):

``` {.language-dart data-language="dart"}
var httpsUri = Uri(
    scheme: 'https',
    host: 'dart.dev',
    path: '/guides/libraries/library-tour',
    fragment: 'numbers');
print(httpsUri); // https://dart.dev/guides/libraries/library-tour#numbers

httpsUri = Uri(
    scheme: 'https',
    host: 'example.com',
    path: '/page/',
    queryParameters: {'search': 'blue', 'limit': '10'});
print(httpsUri); // https://example.com/page/?search=blue&limit=10

final mailtoUri = Uri(
    scheme: 'mailto',
    path: 'John.Doe@example.com',
    queryParameters: {'subject': 'Example'});
print(mailtoUri); // mailto:John.Doe@example.com?subject=Example
```

HTTP and HTTPS URI
------------------

To create a URI with https scheme, use [Uri.https](uri/uri.https) or
[Uri.http](uri/uri.http):

``` {.language-dart data-language="dart"}
final httpsUri = Uri.https('example.com', 'api/fetch', {'limit': '10'});
print(httpsUri); // https://example.com/api/fetch?limit=10
```

File URI
--------

To create a URI from file path, use [Uri.file](uri/uri.file):

``` {.language-dart data-language="dart"}
final fileUriUnix =
    Uri.file(r'/home/myself/images/image.png', windows: false);
print(fileUriUnix); // file:///home/myself/images/image.png

final fileUriWindows =
    Uri.file(r'C:\Users\myself\Documents\image.png', windows: true);
print(fileUriWindows); // file:///C:/Users/myself/Documents/image.png
```

If the URI is not a file URI, calling this throws
[UnsupportedError](unsupportederror-class).

Directory URI
-------------

Like [Uri.file](uri/uri.file) except that a non-empty URI path ends in a
slash.

``` {.language-dart data-language="dart"}
final fileDirectory =
    Uri.directory('/home/myself/data/image', windows: false);
print(fileDirectory); // file:///home/myself/data/image/

final fileDirectoryWindows = Uri.directory('/data/images', windows: true);
print(fileDirectoryWindows); //  file:///data/images/
```

URI from string
---------------

To create a URI from string, use [Uri.parse](uri/parse) or
[Uri.tryParse](uri/tryparse):

``` {.language-dart data-language="dart"}
final uri = Uri.parse(
    'https://dart.dev/guides/libraries/library-tour#utility-classes');
print(uri); // https://dart.dev
print(uri.isScheme('https')); // true
print(uri.origin); // https://dart.dev
print(uri.host); // dart.dev
print(uri.authority); // dart.dev
print(uri.port); // 443
print(uri.path); // guides/libraries/library-tour
print(uri.pathSegments); // [guides, libraries, library-tour]
print(uri.fragment); // utility-classes
print(uri.hasQuery); // false
print(uri.data); // null
```

**See also:**

-   [URIs](https://dart.dev/guides/libraries/library-tour#uris) in the
    [library tour](https://dart.dev/guides/libraries/library-tour)
-   [RFC-3986](https://tools.ietf.org/html/rfc3986)
-   [RFC-2396](https://tools.ietf.org/html/rfc2396)
-   [RFC-2045](https://tools.ietf.org/html/rfc2045)

Constructors
------------

[Uri](uri/uri)({[String](string-class)? scheme, [String](string-class)?
userInfo, [String](string-class)? host, [int](int-class)? port,
[String](string-class)? path,
[Iterable](iterable-class)\<[String](string-class)\>? pathSegments,
[String](string-class)? query, [Map](map-class)\<[String](string-class),
dynamic\>? queryParameters, [String](string-class)? fragment})

::: {.constructor-modifier .features}
factory
:::

Creates a new URI from its components.

[Uri.dataFromBytes](uri/uri.datafrombytes)([List](list-class)\<[int](int-class)\>
bytes, {[String](string-class) mimeType = \"application/octet-stream\",
[Map](map-class)\<[String](string-class), [String](string-class)\>?
parameters, [bool](bool-class) percentEncoded = false})

::: {.constructor-modifier .features}
factory
:::

Creates a `data:` URI containing an encoding of `bytes`.

[Uri.dataFromString](uri/uri.datafromstring)([String](string-class)
content, {[String](string-class)? mimeType,
[Encoding](../dart-convert/encoding-class)? encoding,
[Map](map-class)\<[String](string-class), [String](string-class)\>?
parameters, [bool](bool-class) base64 = false})

::: {.constructor-modifier .features}
factory
:::

Creates a `data:` URI containing the `content` string.

[Uri.directory](uri/uri.directory)([String](string-class) path,
{[bool](bool-class)? windows})

::: {.constructor-modifier .features}
factory
:::

Like [Uri.file](uri/uri.file) except that a non-empty URI path ends in a
slash.

[Uri.file](uri/uri.file)([String](string-class) path,
{[bool](bool-class)? windows})

::: {.constructor-modifier .features}
factory
:::

Creates a new file URI from an absolute or relative file path.

[Uri.http](uri/uri.http)([String](string-class) authority,
\[[String](string-class) unencodedPath,
[Map](map-class)\<[String](string-class), dynamic\>? queryParameters\])

::: {.constructor-modifier .features}
factory
:::

Creates a new `http` URI from authority, path and query.

[Uri.https](uri/uri.https)([String](string-class) authority,
\[[String](string-class) unencodedPath,
[Map](map-class)\<[String](string-class), dynamic\>? queryParameters\])

::: {.constructor-modifier .features}
factory
:::

Creates a new `https` URI from authority, path and query.

Properties {#instance-properties}
----------

[authority](uri/authority) → [String](string-class)

::: {.features}
read-only
:::

The authority component.

[data](uri/data) → [UriData](uridata-class)?

::: {.features}
read-only
:::

Access the structure of a `data:` URI.

[fragment](uri/fragment) → [String](string-class)

::: {.features}
read-only
:::

The fragment identifier component.

[hasAbsolutePath](uri/hasabsolutepath) → [bool](bool-class)

::: {.features}
read-only
:::

Whether the URI has an absolute path (starting with \'/\').

[hasAuthority](uri/hasauthority) → [bool](bool-class)

::: {.features}
read-only
:::

Whether the URI has an [authority](uri/authority) component.

[hasEmptyPath](uri/hasemptypath) → [bool](bool-class)

::: {.features}
read-only
:::

Whether the URI has an empty path.

[hasFragment](uri/hasfragment) → [bool](bool-class)

::: {.features}
read-only
:::

Whether the URI has a fragment part.

[hashCode](uri/hashcode) → [int](int-class)

::: {.features}
read-only, override
:::

Returns a hash code computed as `toString().hashCode`.

[hasPort](uri/hasport) → [bool](bool-class)

::: {.features}
read-only
:::

Whether the URI has an explicit port.

[hasQuery](uri/hasquery) → [bool](bool-class)

::: {.features}
read-only
:::

Whether the URI has a query part.

[hasScheme](uri/hasscheme) → [bool](bool-class)

::: {.features}
read-only
:::

Whether the URI has a [scheme](uri/scheme) component.

[host](uri/host) → [String](string-class)

::: {.features}
read-only
:::

The host part of the authority component.

[isAbsolute](uri/isabsolute) → [bool](bool-class)

::: {.features}
read-only
:::

Whether the URI is absolute.

[origin](uri/origin) → [String](string-class)

::: {.features}
read-only
:::

Returns the origin of the URI in the form scheme://host:port for the
schemes http and https.

[path](uri/path) → [String](string-class)

::: {.features}
read-only
:::

The path component.

[pathSegments](uri/pathsegments) →
[List](list-class)\<[String](string-class)\>

::: {.features}
read-only
:::

The URI path split into its segments.

[port](uri/port) → [int](int-class)

::: {.features}
read-only
:::

The port part of the authority component.

[query](uri/query) → [String](string-class)

::: {.features}
read-only
:::

The query component.

[queryParameters](uri/queryparameters) →
[Map](map-class)\<[String](string-class), [String](string-class)\>

::: {.features}
read-only
:::

The URI query split into a map according to the rules specified for FORM
post in the [HTML 4.01 specification section
17.13.4](https://www.w3.org/TR/REC-html40/interact/forms.html#h-17.13.4 "HTML 4.01 section 17.13.4").

[queryParametersAll](uri/queryparametersall) →
[Map](map-class)\<[String](string-class),
[List](list-class)\<[String](string-class)\>\>

::: {.features}
read-only
:::

Returns the URI query split into a map according to the rules specified
for FORM post in the [HTML 4.01 specification section
17.13.4](https://www.w3.org/TR/REC-html40/interact/forms.html#h-17.13.4 "HTML 4.01 section 17.13.4").

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[scheme](uri/scheme) → [String](string-class)

::: {.features}
read-only
:::

The scheme component of the URI.

[userInfo](uri/userinfo) → [String](string-class)

::: {.features}
read-only
:::

The user info part of the authority component.

Methods {#instance-methods}
-------

[isScheme](uri/isscheme)([String](string-class) scheme) →
[bool](bool-class)

Whether the scheme of this [Uri](uri-class) is `scheme`.

[normalizePath](uri/normalizepath)() → [Uri](uri-class)

Returns a URI where the path has been normalized.

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[removeFragment](uri/removefragment)() → [Uri](uri-class)

Creates a `Uri` that differs from this only in not having a fragment.

[replace](uri/replace)({[String](string-class)? scheme,
[String](string-class)? userInfo, [String](string-class)? host,
[int](int-class)? port, [String](string-class)? path,
[Iterable](iterable-class)\<[String](string-class)\>? pathSegments,
[String](string-class)? query, [Map](map-class)\<[String](string-class),
dynamic\>? queryParameters, [String](string-class)? fragment}) →
[Uri](uri-class)

Creates a new `Uri` based on this one, but with some parts replaced.

[resolve](uri/resolve)([String](string-class) reference) →
[Uri](uri-class)

Resolve `reference` as an URI relative to `this`.

[resolveUri](uri/resolveuri)([Uri](uri-class) reference) →
[Uri](uri-class)

Resolve `reference` as a URI relative to `this`.

[toFilePath](uri/tofilepath)({[bool](bool-class)? windows}) →
[String](string-class)

Creates a file path from a file URI.

[toString](uri/tostring)() → [String](string-class)

::: {.features}
override
:::

The normalized string representation of the URI.

Operators
---------

[operator ==](uri/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
override
:::

A URI is equal to another URI with the same normalized representation.

Static Properties
-----------------

[base](uri/base) → [Uri](uri-class)

::: {.features}
read-only
:::

The natural base URI for the current platform.

Static Methods
--------------

[decodeComponent](uri/decodecomponent)([String](string-class) encodedComponent) → [String](string-class)
:   Decodes the percent-encoding in `encodedComponent`.

[decodeFull](uri/decodefull)([String](string-class) uri) → [String](string-class)
:   Decodes the percent-encoding in `uri`.

[decodeQueryComponent](uri/decodequerycomponent)([String](string-class) encodedComponent, {[Encoding](../dart-convert/encoding-class) encoding = utf8}) → [String](string-class)
:   Decodes the percent-encoding in `encodedComponent`, converting
    pluses to spaces.

[encodeComponent](uri/encodecomponent)([String](string-class) component) → [String](string-class)
:   Encode the string `component` using percent-encoding to make it safe
    for literal use as a URI component.

[encodeFull](uri/encodefull)([String](string-class) uri) → [String](string-class)
:   Encodes the string `uri` using percent-encoding to make it safe for
    literal use as a full URI.

[encodeQueryComponent](uri/encodequerycomponent)([String](string-class) component, {[Encoding](../dart-convert/encoding-class) encoding = utf8}) → [String](string-class)
:   Encodes the string `component` according to the HTML 4.01 rules for
    encoding the posting of a HTML form as a query string component.

[parse](uri/parse)([String](string-class) uri, \[[int](int-class) start = 0, [int](int-class)? end\]) → [Uri](uri-class)
:   Creates a new `Uri` object by parsing a URI string.

[parseIPv4Address](uri/parseipv4address)([String](string-class) host) → [List](list-class)\<[int](int-class)\>
:   Parses the `host` as an IP version 4 (IPv4) address, returning the
    address as a list of 4 bytes in network byte order (big endian).

[parseIPv6Address](uri/parseipv6address)([String](string-class) host, \[[int](int-class) start = 0, [int](int-class)? end\]) → [List](list-class)\<[int](int-class)\>
:   Parses the `host` as an IP version 6 (IPv6) address.

[splitQueryString](uri/splitquerystring)([String](string-class) query, {[Encoding](../dart-convert/encoding-class) encoding = utf8}) → [Map](map-class)\<[String](string-class), [String](string-class)\>
:   Splits the `query` into a map according to the rules specified for
    FORM post in the [HTML 4.01 specification section
    17.13.4](https://www.w3.org/TR/REC-html40/interact/forms.html#h-17.13.4 "HTML 4.01 section 17.13.4").

[tryParse](uri/tryparse)([String](string-class) uri, \[[int](int-class) start = 0, [int](int-class)? end\]) → [Uri](uri-class)?
:   Creates a new `Uri` object by parsing a URI string.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri-class.html>
:::
