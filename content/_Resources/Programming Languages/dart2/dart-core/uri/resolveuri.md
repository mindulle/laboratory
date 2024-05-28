[dart:core](../../dart-core/dart-core-library){._links-link}

resolveUri method
=================

::: {.section .multi-line-signature}
[Uri](../uri-class) resolveUri(

1.  [Uri](../uri-class) reference

)
:::

Resolve `reference` as a URI relative to `this`.

Returns the resolved URI.

The algorithm \"Transform Reference\" for resolving a reference is
described in [RFC-3986 Section
5](https://tools.ietf.org/html/rfc3986#section-5 "RFC-1123").

Updated to handle the case where the base URI is just a relative path -
that is: when it has no scheme and no authority and the path does not
start with a slash. In that case, the paths are combined without
removing leading \"..\", and an empty path is not converted to \"/\".

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uri resolveUri(Uri reference);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/resolveUri.html>
:::
