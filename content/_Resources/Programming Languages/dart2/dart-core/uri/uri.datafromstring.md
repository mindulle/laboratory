[dart:core](../../dart-core/dart-core-library){._links-link}

Uri.dataFromString constructor
==============================

::: {.section .multi-line-signature}
Uri.dataFromString(

1.  [String](../string-class) content,
2.  {[String](../string-class)? mimeType,
3.  [Encoding](../../dart-convert/encoding-class)? encoding,
4.  [Map](../map-class)\<[String](../string-class),
    [String](../string-class)\>? parameters,
5.  [bool](../bool-class) base64 = false}

)
:::

Creates a `data:` URI containing the `content` string.

Converts the content to bytes using `encoding` or the charset specified
in `parameters` (defaulting to US-ASCII if not specified or
unrecognized), then encodes the bytes into the resulting data URI.

Defaults to encoding using percent-encoding (any non-ASCII or
non-URI-valid bytes is replaced by a percent encoding). If `base64` is
true, the bytes are instead encoded using `base64`.

If `encoding` is not provided and `parameters` has a `charset` entry,
that name is looked up using
[Encoding.getByName](../../dart-convert/encoding/getbyname), and if the
lookup returns an encoding, that encoding is used to convert `content`
to bytes. If providing both an `encoding` and a charset in `parameters`,
they should agree, otherwise decoding won\'t be able to use the charset
parameter to determine the encoding.

If `mimeType` and/or `parameters` are supplied, they are added to the
created URI. If any of these contain characters that are not allowed in
the data URI, the character is percent-escaped. If the character is
non-ASCII, it is first UTF-8 encoded and then the bytes are percent
encoded. An omitted `mimeType` in a data URI means `text/plain`, just as
an omitted `charset` parameter defaults to meaning `US-ASCII`.

To read the content back, use
[UriData.contentAsString](../uridata/contentasstring).

Example:

``` {.language-dart data-language="dart"}
final uri = Uri.dataFromString(
  'example content',
  mimeType: 'text/plain',
  parameters: <String, String>{'search': 'file', 'max': '10'},
);
print(uri); // data:;search=name;max=10,example%20content
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Uri.dataFromString(String content,
    {String? mimeType,
    Encoding? encoding,
    Map<String, String>? parameters,
    bool base64 = false}) {
  UriData data = UriData.fromString(content,
      mimeType: mimeType,
      encoding: encoding,
      parameters: parameters,
      base64: base64);
  return data.uri;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/Uri.dataFromString.html>
:::
