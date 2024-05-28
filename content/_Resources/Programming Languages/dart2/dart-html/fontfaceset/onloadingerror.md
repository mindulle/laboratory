[dart:html](../../dart-html/dart-html-library){._links-link}

onLoadingError property
=======================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[FontFaceSetLoadEvent](../fontfacesetloadevent-class)\>
onLoadingError
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<FontFaceSetLoadEvent> get onLoadingError =>
    loadingErrorEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/FontFaceSet/onLoadingError.html>
:::
