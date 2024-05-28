[dart:core](../../dart-core/dart-core-library){._links-link}

mimeType property
=================

::: {#getter .section .multi-line-signature}
[String](../string-class) mimeType
:::

The MIME type of the data URI.

A data URI consists of a \"media type\" followed by data. The media type
starts with a MIME type and can be followed by extra parameters. If the
MIME type representation in the URI text contains URI escapes, they are
unescaped in the returned string. If the value contain non-ASCII percent
escapes, they are decoded as UTF-8.

Example:

``` {.language-dart data-language="dart"}
data:text/plain;charset=utf-8,Hello%20World!
```

This data URI has the media type `text/plain;charset=utf-8`, which is
the MIME type `text/plain` with the parameter `charset` with value
`utf-8`. See [RFC 2045](https://tools.ietf.org/html/rfc2045) for more
detail.

If the first part of the data URI is empty, it defaults to `text/plain`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get mimeType {
  int start = _separatorIndices[0] + 1;
  int end = _separatorIndices[1];
  if (start == end) return "text/plain";
  return _Uri._uriDecode(_text, start, end, utf8, false);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/UriData/mimeType.html>
:::
