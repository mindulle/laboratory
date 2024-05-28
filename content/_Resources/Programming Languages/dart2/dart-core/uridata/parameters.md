[dart:core](../../dart-core/dart-core-library){._links-link}

parameters property
===================

::: {#getter .section .multi-line-signature}
[Map](../map-class)\<[String](../string-class),
[String](../string-class)\> parameters
:::

A map representing the parameters of the media type.

A data URI may contain parameters between the MIME type and the data.
This converts these parameters to a map from parameter name to parameter
value. The map only contains parameters that actually occur in the URI.
The `charset` parameter has a default value even if it doesn\'t occur in
the URI, which is reflected by the [charset](charset) getter. This means
that [charset](charset) may return a value even if
`parameters["charset"]` is `null`.

If the values contain non-ASCII values or percent escapes, they are
decoded as UTF-8.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Map<String, String> get parameters {
  var result = <String, String>{};
  for (int i = 3; i < _separatorIndices.length; i += 2) {
    var start = _separatorIndices[i - 2] + 1;
    var equals = _separatorIndices[i - 1];
    var end = _separatorIndices[i];
    String key = _Uri._uriDecode(_text, start, equals, utf8, false);
    String value = _Uri._uriDecode(_text, equals + 1, end, utf8, false);
    result[key] = value;
  }
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/UriData/parameters.html>
:::
