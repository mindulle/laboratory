[dart:html](../../dart-html/dart-html-library){._links-link}

scrollLeft property
===================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) scrollLeft
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get scrollLeft => JS<num>('num', '#.scrollLeft', this).round();
```

::: {#setter .section .multi-line-signature}
void scrollLeft=([int](../../dart-core/int-class) value)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set scrollLeft(int value) {
  JS("void", "#.scrollLeft = #", this, value.round());
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/scrollLeft.html>
:::
