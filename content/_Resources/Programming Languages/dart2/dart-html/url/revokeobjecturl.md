[dart:html](../../dart-html/dart-html-library){._links-link}

revokeObjectUrl method
======================

::: {.section .multi-line-signature}
void revokeObjectUrl(

1.  [String](../../dart-core/string-class) url

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static void revokeObjectUrl(String url) =>
    JS('void', '(self.URL || self.webkitURL).revokeObjectURL(#)', url);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Url/revokeObjectUrl.html>
:::
