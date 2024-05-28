[dart:core](../../dart-core/dart-core-library){._links-link}

isMimeType method
=================

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.17\")

</div>

[bool](../bool-class) isMimeType(

1.  [String](../string-class) mimeType

)

::: {.features}
\@Since(\"2.17\")
:::
:::

Whether the [UriData.mimeType](mimetype) is equal to `mimeType`.

Compares the `data:` URI\'s MIME type to `mimeType` with a case-
insensitive comparison which ignores the case of ASCII letters.

An empty `mimeType` is considered equivalent to `text/plain`, both in
the `mimeType` argument and in the `data:` URI itself.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.17")
bool isMimeType(String mimeType) {
  int start = _separatorIndices[0] + 1;
  int end = _separatorIndices[1];
  if (start == end) {
    return mimeType.isEmpty ||
        identical(mimeType, "text/plain") ||
        _caseInsensitiveEquals(mimeType, "text/plain");
  }
  if (mimeType.isEmpty) mimeType = "text/plain";
  return (mimeType.length == end - start) &&
      _caseInsensitiveStartsWith(mimeType, _text, start);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/UriData/isMimeType.html>
:::
