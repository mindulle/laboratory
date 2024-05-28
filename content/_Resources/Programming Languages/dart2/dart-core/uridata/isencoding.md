[dart:core](../../dart-core/dart-core-library){._links-link}

isEncoding method
=================

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.17\")

</div>

[bool](../bool-class) isEncoding(

1.  [Encoding](../../dart-convert/encoding-class) encoding

)

::: {.features}
\@Since(\"2.17\")
:::
:::

Whether the charset parameter represents `encoding`.

If the \"charset\" parameter is not present in the URI, it defaults to
\"US-ASCII\", which is the [ascii](../../dart-convert/ascii-constant)
encoding. If present, it\'s converted to an
[Encoding](../../dart-convert/encoding-class) using
[Encoding.getByName](../../dart-convert/encoding/getbyname), and
compared to `encoding`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.17")
bool isEncoding(Encoding encoding) {
  var charsetIndex = _findCharsetIndex();
  if (charsetIndex < 0) {
    return identical(encoding, ascii);
  }
  var valueStart = _separatorIndices[charsetIndex + 1] + 1;
  var valueEnd = _separatorIndices[charsetIndex + 2];
  return identical(
      encoding,
      Encoding.getByName(
          _Uri._uriDecode(_text, valueStart, valueEnd, utf8, false)));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/UriData/isEncoding.html>
:::
