[dart:html](../../dart-html/dart-html-library){._links-link}

VideoElement constructor
========================

::: {.section .multi-line-signature}
VideoElement()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory VideoElement() => JS<VideoElement>(
    'returns:VideoElement;creates:VideoElement;new:true',
    '#.createElement(#)',
    document,
    "video");
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/VideoElement/VideoElement.html>
:::
