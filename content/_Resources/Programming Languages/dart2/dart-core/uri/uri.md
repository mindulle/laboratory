[dart:core](../../dart-core/dart-core-library){._links-link}

Uri constructor
===============

::: {.section .multi-line-signature}
Uri(

1.  {[String](../string-class)? scheme,
2.  [String](../string-class)? userInfo,
3.  [String](../string-class)? host,
4.  [int](../int-class)? port,
5.  [String](../string-class)? path,
6.  [Iterable](../iterable-class)\<[String](../string-class)\>?
    pathSegments,
7.  [String](../string-class)? query,
8.  [Map](../map-class)\<[String](../string-class), dynamic\>?
    queryParameters,
9.  [String](../string-class)? fragment}

)
:::

Creates a new URI from its components.

Each component is set through a named argument. Any number of components
can be provided. The `path` and `query` components can be set using
either of two different named arguments.

The scheme component is set through `scheme`. The scheme is normalized
to all lowercase letters. If the scheme is omitted or empty, the URI
will not have a scheme part.

The user info part of the authority component is set through `userInfo`.
It defaults to the empty string, which will be omitted from the string
representation of the URI.

The host part of the authority component is set through `host`. The host
can either be a hostname, an IPv4 address or an IPv6 address, contained
in `'['` and `']'`. If the host contains a \':\' character, the `'['`
and `']'` are added if not already provided. The host is normalized to
all lowercase letters.

The port part of the authority component is set through `port`. If
`port` is omitted or `null`, it implies the default port for the URI\'s
scheme, and is equivalent to passing that port explicitly. The
recognized schemes, and their default ports, are \"http\" (80) and
\"https\" (443). All other schemes are considered as having zero as the
default port.

If any of `userInfo`, `host` or `port` are provided, the URI has an
authority according to [hasAuthority](hasauthority).

The path component is set through either `path` or `pathSegments`. When
`path` is used, it should be a valid URI path, but invalid characters,
except the general delimiters \':/@\[\]?\#\', will be escaped if
necessary. A backslash, `\`, will be converted to a slash `/`. When
`pathSegments` is used, each of the provided segments is first
percent-encoded and then joined using the forward slash separator.

The percent-encoding of the path segments encodes all characters except
for the unreserved characters and the following list of characters:
`!$&'()*+,;=:@`. If the other components necessitate an absolute path, a
leading slash `/` is prepended if not already there.

The query component is set through either `query` or `queryParameters`.
When `query` is used, the provided string should be a valid URI query,
but invalid characters, other than general delimiters, will be escaped
if necessary. When `queryParameters` is used, the query is built from
the provided map. Each key and value in the map is percent-encoded and
joined using equal and ampersand characters. A value in the map must be
either a string, or an [Iterable](../iterable-class) of strings, where
the latter corresponds to multiple values for the same key.

The percent-encoding of the keys and values encodes all characters
except for the unreserved characters, and replaces spaces with `+`. If
`query` is the empty string, it is equivalent to omitting it. To have an
actual empty query part, use an empty map for `queryParameters`.

If both `query` and `queryParameters` are omitted or `null`, the URI has
no query part.

The fragment component is set through `fragment`. It should be a valid
URI fragment, but invalid characters other than general delimiters are
escaped if necessary. If `fragment` is omitted or `null`, the URI has no
fragment part.

Example:

``` {.language-dart data-language="dart"}
final httpsUri = Uri(
    scheme: 'https',
    host: 'dart.dev',
    path: 'guides/libraries/library-tour',
    fragment: 'numbers');
print(httpsUri); // https://dart.dev/guides/libraries/library-tour#numbers

final mailtoUri = Uri(
    scheme: 'mailto',
    path: 'John.Doe@example.com',
    queryParameters: {'subject': 'Example'});
print(mailtoUri); // mailto:John.Doe@example.com?subject=Example
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Uri(
    {String? scheme,
    String? userInfo,
    String? host,
    int? port,
    String? path,
    Iterable<String>? pathSegments,
    String? query,
    Map<String, dynamic /*String|Iterable<String>*/ >? queryParameters,
    String? fragment}) = _Uri;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/Uri.html>
:::
