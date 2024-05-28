[dart:core](../../dart-core/dart-core-library){._links-link}

isCharset method
================

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.17\")

</div>

[bool](../bool-class) isCharset(

1.  [String](../string-class) charset

)

::: {.features}
\@Since(\"2.17\")
:::
:::

Checks whether the charset parameter of the mime type is `charset`.

If this URI has no \"charset\" parameter, it is assumed to have a
default of `charset=US-ASCII`. If `charset` is empty, it\'s treated like
`"US-ASCII"`.

Returns true if `charset` and the \"charset\" parameter value are equal
strings, ignoring the case of ASCII letters, or both correspond to the
same [Encoding](../../dart-convert/encoding-class), as given by
[Encoding.getByName](../../dart-convert/encoding/getbyname).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.17")
bool isCharset(String charset) {
  var charsetIndex = _findCharsetIndex();
  if (charsetIndex < 0) {
    return charset.isEmpty ||
        _caseInsensitiveEquals(charset, "US-ASCII") ||
        identical(Encoding.getByName(charset), ascii);
  }
  if (charset.isEmpty) charset = "US-ASCII";
  var valueStart = _separatorIndices[charsetIndex + 1] + 1;
  var valueEnd = _separatorIndices[charsetIndex + 2];
  var length = valueEnd - valueStart;
  if (charset.length == length &&
      _caseInsensitiveStartsWith(charset, _text, valueStart)) {
    return true;
  }
  var checkedEncoding = Encoding.getByName(charset);
  return checkedEncoding != null &&
      identical(
          checkedEncoding,
          Encoding.getByName(
              _Uri._uriDecode(_text, valueStart, valueEnd, utf8, false)));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/UriData/isCharset.html>
:::
