[dart:io](../../dart-io/dart-io-library){._links-link}

File.fromUri constructor
========================

::: {.section .multi-line-signature}
File.fromUri(

1.  [Uri](../../dart-core/uri-class) uri

)
:::

Create a [File](../file-class) object from a URI.

If `uri` cannot reference a file this throws
[UnsupportedError](../../dart-core/unsupportederror-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory File.fromUri(Uri uri) => new File(uri.toFilePath());
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/File.fromUri.html>
:::
