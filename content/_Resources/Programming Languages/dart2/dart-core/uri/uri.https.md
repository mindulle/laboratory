[dart:core](../../dart-core/dart-core-library){._links-link}

Uri.https constructor
=====================

::: {.section .multi-line-signature}
Uri.https(

1.  [String](../string-class) authority,
2.  \[[String](../string-class) unencodedPath,
3.  [Map](../map-class)\<[String](../string-class), dynamic\>?
    queryParameters\]

)
:::

Creates a new `https` URI from authority, path and query.

This constructor is the same as [Uri.http](uri.http) except for the
scheme which is set to `https`.

Example:

``` {.language-dart data-language="dart"}
var uri = Uri.https('example.org', '/path', {'q': 'dart'});
print(uri); // https://example.org/path?q=dart

uri = Uri.https('user:password@localhost:8080', '');
print(uri); // https://user:password@localhost:8080

uri = Uri.https('example.org', 'a b');
print(uri); // https://example.org/a%20b

uri = Uri.https('example.org', '/a%2F');
print(uri); // https://example.org/a%252F
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Uri.https(String authority,
    [String unencodedPath,
    Map<String, dynamic>? queryParameters]) = _Uri.https;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/Uri.https.html>
:::
