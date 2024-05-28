[dart:html](../../dart-html/dart-html-library){._links-link}

scrollWidth property
====================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) scrollWidth
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get scrollWidth => JS<num>('num', '#.scrollWidth', this).round();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/scrollWidth.html>
:::
