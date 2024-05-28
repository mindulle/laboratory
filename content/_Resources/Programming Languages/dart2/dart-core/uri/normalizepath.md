[dart:core](../../dart-core/dart-core-library){._links-link}

normalizePath method
====================

::: {.section .multi-line-signature}
[Uri](../uri-class) normalizePath()
:::

Returns a URI where the path has been normalized.

A normalized path does not contain `.` segments or non-leading `..`
segments. Only a relative path with no scheme or authority may contain
leading `..` segments; a path that starts with `/` will also drop any
leading `..` segments.

This uses the same normalization strategy as `Uri().resolve(this)`.

Does not change any part of the URI except the path.

The default implementation of `Uri` always normalizes paths, so calling
this function has no effect.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uri normalizePath();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/normalizePath.html>
:::
