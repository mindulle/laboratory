[dart:io](../../dart-io/dart-io-library){._links-link}

Link.fromUri constructor
========================

::: {.section .multi-line-signature}
Link.fromUri(

1.  [Uri](../../dart-core/uri-class) uri

)
:::

Creates a [Link](../link-class) object.

If [path](../filesystementity/path) is a relative path, it will be
interpreted relative to the current working directory (see
[Directory.current](../directory/current)), when used.

If [path](../filesystementity/path) is an absolute path, it will be
immune to changes to the current working directory.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Link.fromUri(Uri uri) => new Link(uri.toFilePath());
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Link/Link.fromUri.html>
:::
