[dart:core](../../dart-core/dart-core-library){._links-link}

Uri.http constructor
====================

::: {.section .multi-line-signature}
Uri.http(

1.  [String](../string-class) authority,
2.  \[[String](../string-class) unencodedPath,
3.  [Map](../map-class)\<[String](../string-class), dynamic\>?
    queryParameters\]

)
:::

Creates a new `http` URI from authority, path and query.

Example:

``` {.language-dart data-language="dart"}
var uri = Uri.http('example.org', '/path', { 'q' : 'dart' });
print(uri); // http://example.org/path?q=dart

uri = Uri.http('user:password@localhost:8080', '');
print(uri); // http://user:password@localhost:8080

uri = Uri.http('example.org', 'a b');
print(uri); // http://example.org/a%20b

uri = Uri.http('example.org', '/a%2F');
print(uri); // http://example.org/a%252F
```

The `scheme` is always set to `http`.

The `userInfo`, `host` and `port` components are set from the
`authority` argument. If `authority` is `null` or empty, the created
`Uri` has no authority, and isn\'t directly usable as an HTTP URL, which
must have a non-empty host.

The `path` component is set from the `unencodedPath` argument. The path
passed must not be encoded as this constructor encodes the path. Only
`/` is recognized as path separtor. If omitted, the path defaults to
being empty.

The `query` component is set from the optional `queryParameters`
argument.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Uri.http(String authority,
    [String unencodedPath,
    Map<String, dynamic>? queryParameters]) = _Uri.http;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/Uri.http.html>
:::
