[dart:html](../../dart-html/dart-html-library){._links-link}

createObjectUrlFromBlob method
==============================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) createObjectUrlFromBlob(

1.  [Blob](../blob-class) blob

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String createObjectUrlFromBlob(Blob blob) =>
    JS('String', '(self.URL || self.webkitURL).createObjectURL(#)', blob);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Url/createObjectUrlFromBlob.html>
:::
