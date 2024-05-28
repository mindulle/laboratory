[dart:core](../../dart-core/dart-core-library){._links-link}

Uri.dataFromBytes constructor
=============================

::: {.section .multi-line-signature}
Uri.dataFromBytes(

1.  [List](../list-class)\<[int](../int-class)\> bytes,
2.  {[String](../string-class) mimeType = \"application/octet-stream\",
3.  [Map](../map-class)\<[String](../string-class),
    [String](../string-class)\>? parameters,
4.  [bool](../bool-class) percentEncoded = false}

)
:::

Creates a `data:` URI containing an encoding of `bytes`.

Defaults to Base64 encoding the bytes, but if `percentEncoded` is
`true`, the bytes will instead be percent encoded (any non-ASCII or
non-valid-ASCII-character byte is replaced by a percent encoding).

To read the bytes back, use
[UriData.contentAsBytes](../uridata/contentasbytes).

It defaults to having the mime-type `application/octet-stream`. The
`mimeType` and `parameters` are added to the created URI. If any of
these contain characters that are not allowed in the data URI, the
character is percent-escaped. If the character is non-ASCII, it is first
UTF-8 encoded and then the bytes are percent encoded.

Example:

``` {.language-dart data-language="dart"}
final uri = Uri.dataFromBytes([68, 97, 114, 116]);
print(uri); // data:application/octet-stream;base64,RGFydA==
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Uri.dataFromBytes(List<int> bytes,
    {String mimeType = "application/octet-stream",
    Map<String, String>? parameters,
    bool percentEncoded = false}) {
  UriData data = UriData.fromBytes(bytes,
      mimeType: mimeType,
      parameters: parameters,
      percentEncoded: percentEncoded);
  return data.uri;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/Uri.dataFromBytes.html>
:::
