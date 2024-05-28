[dart:html](../../dart-html/dart-html-library){._links-link}

client property
===============

::: {#getter .section .multi-line-signature}
[Rectangle](../../dart-math/rectangle-class)\<[num](../../dart-core/num-class)\>
client
:::

Gets the position of this element relative to the client area of the
page.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Rectangle get client =>
    new Rectangle(clientLeft!, clientTop!, clientWidth, clientHeight);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/client.html>
:::
