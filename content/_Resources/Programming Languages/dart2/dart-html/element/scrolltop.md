[dart:html](../../dart-html/dart-html-library){._links-link}

scrollTop property
==================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) scrollTop
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get scrollTop => JS<num>('num', '#.scrollTop', this).round();
```

::: {#setter .section .multi-line-signature}
void scrollTop=([int](../../dart-core/int-class) value)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set scrollTop(int value) {
  JS("void", "#.scrollTop = #", this, value.round());
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/scrollTop.html>
:::
