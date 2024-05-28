[dart:core](../../dart-core/dart-core-library){._links-link}

decodeFull method
=================

::: {.section .multi-line-signature}
[String](../string-class) decodeFull(

1.  [String](../string-class) uri

)
:::

Decodes the percent-encoding in `uri`.

Note that decoding a full URI might change its meaning as some of the
decoded characters could be reserved characters. In most cases, an
encoded URI should be parsed into components using [Uri.parse](parse)
before decoding the separate components.

Example:

``` {.language-dart data-language="dart"}
final decoded =
    Uri.decodeFull('https://example.com/api/query?search=%20dart%20is');
print(decoded); // https://example.com/api/query?search= dart is
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String decodeFull(String uri) {
  return _Uri._uriDecode(uri, 0, uri.length, utf8, false);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/decodeFull.html>
:::
