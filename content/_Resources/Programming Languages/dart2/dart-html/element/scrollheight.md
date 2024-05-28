[dart:html](../../dart-html/dart-html-library){._links-link}

scrollHeight property
=====================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) scrollHeight
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get scrollHeight => JS<num>('num', '#.scrollHeight', this).round();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/scrollHeight.html>
:::
