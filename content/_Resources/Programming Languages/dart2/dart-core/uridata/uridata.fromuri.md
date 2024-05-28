[dart:core](../../dart-core/dart-core-library){._links-link}

UriData.fromUri constructor
===========================

::: {.section .multi-line-signature}
UriData.fromUri(

1.  [Uri](../uri-class) uri

)
:::

Creates a `DataUri` from a [Uri](../uri-class) which must have `data` as
[Uri.scheme](../uri/scheme).

The `uri` must have scheme `data` and no authority or fragment, and the
path (concatenated with the query, if there is one) must be valid as
data URI content with the same rules as [parse](parse).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory UriData.fromUri(Uri uri) {
  if (!uri.isScheme("data")) {
    throw ArgumentError.value(uri, "uri", "Scheme must be 'data'");
  }
  if (uri.hasAuthority) {
    throw ArgumentError.value(uri, "uri", "Data uri must not have authority");
  }
  if (uri.hasFragment) {
    throw ArgumentError.value(
        uri, "uri", "Data uri must not have a fragment part");
  }
  if (!uri.hasQuery) {
    return _parse(uri.path, 0, uri);
  }
  // Includes path and query (and leading "data:").
  return _parse(uri.toString(), 5, uri);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/UriData/UriData.fromUri.html>
:::
