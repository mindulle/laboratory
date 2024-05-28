[dart:html](../../dart-html/dart-html-library){._links-link}

createObjectUrlFromSource method
================================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) createObjectUrlFromSource(

1.  [MediaSource](../mediasource-class) source

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String createObjectUrlFromSource(MediaSource source) =>
    JS('String', '(self.URL || self.webkitURL).createObjectURL(#)', source);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Url/createObjectUrlFromSource.html>
:::
