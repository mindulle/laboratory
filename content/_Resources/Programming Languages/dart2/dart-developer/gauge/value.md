[dart:developer](../../dart-developer/dart-developer-library){._links-link}

value property
==============

::: {#getter .section .multi-line-signature}
[double](../../dart-core/double-class) value
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
double get value => _value;
```

::: {#setter .section .multi-line-signature}
void value=([double](../../dart-core/double-class) v)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set value(double v) {
  if (v < min) {
    v = min;
  } else if (v > max) {
    v = max;
  }
  _value = v;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/Gauge/value.html>
:::
