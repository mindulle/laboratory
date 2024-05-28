[dart:html](../../dart-html/dart-html-library){._links-link}

offset property
===============

::: {#getter .section .multi-line-signature}
[Rectangle](../../dart-math/rectangle-class)\<[num](../../dart-core/num-class)\>
offset
:::

Gets the offset of this element relative to its offsetParent.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Rectangle get offset =>
    new Rectangle(offsetLeft, offsetTop, offsetWidth, offsetHeight);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/offset.html>
:::
