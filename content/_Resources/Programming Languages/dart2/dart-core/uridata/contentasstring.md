[dart:core](../../dart-core/dart-core-library){._links-link}

contentAsString method
======================

::: {.section .multi-line-signature}
[String](../string-class) contentAsString(

1.  {[Encoding](../../dart-convert/encoding-class)? encoding}

)
:::

Creates a string from the content of the data URI.

If the content is Base64 encoded, it will be decoded to bytes and then
decoded to a string using `encoding`. If encoding is omitted, the value
of a `charset` parameter is used if it is recognized by
[Encoding.getByName](../../dart-convert/encoding/getbyname); otherwise
it defaults to the [ascii](../../dart-convert/ascii-constant) encoding,
which is the default encoding for data URIs that do not specify an
encoding.

If the content is not Base64 encoded, it will first have percent-escapes
converted to bytes and then the character codes and byte values are
decoded using `encoding`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String contentAsString({Encoding? encoding}) {
  if (encoding == null) {
    var charset = this.charset; // Returns "US-ASCII" if not present.
    encoding = Encoding.getByName(charset);
    if (encoding == null) {
      throw UnsupportedError("Unknown charset: $charset");
    }
  }
  String text = _text;
  int start = _separatorIndices.last + 1;
  if (isBase64) {
    var converter = base64.decoder.fuse(encoding.decoder);
    return converter.convert(text.substring(start));
  }
  return _Uri._uriDecode(text, start, text.length, encoding, false);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/UriData/contentAsString.html>
:::
