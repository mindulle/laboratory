[dart:html](../../dart-html/dart-html-library){._links-link}

valueAsDate property
====================

::: {#getter .section .multi-line-signature}
[DateTime](../../dart-core/datetime-class) valueAsDate

::: {.features}
override
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
DateTime get valueAsDate =>
    convertNativeToDart_DateTime(this._get_valueAsDate);
```

::: {#setter .section .multi-line-signature}
void valueAsDate=([DateTime](../../dart-core/datetime-class)? value)

::: {.features}
override
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set valueAsDate(DateTime? value) {
  this._set_valueAsDate = convertDartToNative_DateTime(value!);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/InputElement/valueAsDate.html>
:::
