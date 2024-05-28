[dart:html](../../dart-html/dart-html-library){._links-link}

documentOffset property
=======================

::: {#getter .section .multi-line-signature}
[Point](../../dart-math/point-class)\<[num](../../dart-core/num-class)\>
documentOffset
:::

Provides the coordinates of the element relative to the top of the
document.

This method is the Dart equivalent to jQuery\'s
[offset](http://api.jquery.com/offset/) method.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Point get documentOffset => offsetTo(document.documentElement!);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/documentOffset.html>
:::
