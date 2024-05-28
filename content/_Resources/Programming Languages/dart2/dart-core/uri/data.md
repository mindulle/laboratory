[dart:core](../../dart-core/dart-core-library){._links-link}

data property
=============

::: {#getter .section .multi-line-signature}
[UriData](../uridata-class)? data
:::

Access the structure of a `data:` URI.

Returns a [UriData](../uridata-class) object for `data:` URIs and `null`
for all other URIs. The [UriData](../uridata-class) object can be used
to access the media type and data of a `data:` URI.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
UriData? get data;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/data.html>
:::
