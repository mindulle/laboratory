[dart:io](../../dart-io/dart-io-library){._links-link}

Directory.fromUri constructor
=============================

::: {.section .multi-line-signature}
Directory.fromUri(

1.  [Uri](../../dart-core/uri-class) uri

)
:::

Create a [Directory](../directory-class) from a URI.

If `uri` cannot reference a directory this throws
[UnsupportedError](../../dart-core/unsupportederror-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Directory.fromUri(Uri uri) => new Directory(uri.toFilePath());
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Directory/Directory.fromUri.html>
:::
