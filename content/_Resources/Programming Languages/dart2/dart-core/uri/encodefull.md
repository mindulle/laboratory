[dart:core](../../dart-core/dart-core-library){._links-link}

encodeFull method
=================

::: {.section .multi-line-signature}
[String](../string-class) encodeFull(

1.  [String](../string-class) uri

)
:::

Encodes the string `uri` using percent-encoding to make it safe for
literal use as a full URI.

All characters except uppercase and lowercase letters, digits and the
characters `!#$&'()*+,-./:;=?@_~` are percent-encoded. This is the set
of characters specified in in ECMA-262 version 5.1 for the encodeURI
function.

Example:

``` {.language-dart data-language="dart"}
final encoded =
    Uri.encodeFull('https://example.com/api/query?search= dart is');
print(encoded); // https://example.com/api/query?search=%20dart%20is
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String encodeFull(String uri) {
  return _Uri._uriEncode(_Uri._encodeFullTable, uri, utf8, false);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/encodeFull.html>
:::
