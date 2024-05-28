[dart:core](../../dart-core/dart-core-library){._links-link}

uri property
============

::: {#getter .section .multi-line-signature}
[Uri](../uri-class) uri
:::

The [Uri](../uri-class) that this `UriData` is giving access to.

Returns a `Uri` with scheme `data` and the remainder of the data URI as
path.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uri get uri {
  return _uriCache ??= _computeUri();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/UriData/uri.html>
:::
