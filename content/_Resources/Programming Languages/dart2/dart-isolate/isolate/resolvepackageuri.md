[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

resolvePackageUri method
========================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Uri](../../dart-core/uri-class)?\>
resolvePackageUri(

1.  [Uri](../../dart-core/uri-class) packageUri

)
:::

Maps a `package:` URI to a non-package Uri.

If there is no valid mapping from the `package:` URI in the current
isolate, then this call returns `null`. Non-`package:` URIs are returned
unmodified.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static Future<Uri?> resolvePackageUri(Uri packageUri);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Isolate/resolvePackageUri.html>
:::
