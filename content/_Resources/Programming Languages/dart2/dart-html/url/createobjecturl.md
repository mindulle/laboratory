[dart:html](../../dart-html/dart-html-library){._links-link}

createObjectUrl method
======================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) createObjectUrl(

1.  dynamic blob\_OR\_source\_OR\_stream

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String createObjectUrl(blob_OR_source_OR_stream) => JS(
    'String',
    '(self.URL || self.webkitURL).createObjectURL(#)',
    blob_OR_source_OR_stream);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Url/createObjectUrl.html>
:::
