[dart:convert](../../dart-convert/dart-convert-library){._links-link}

cast\<RS, RT\> method
=====================

::: {.section .multi-line-signature}
[Converter](../converter-class)\<RS, RT\> cast\<RS, RT\>()

::: {.features}
override
:::
:::

Provides a `Converter<RS, RT>` view of this stream transformer.

The resulting transformer will check at run-time that all conversion
inputs are actually instances of `S`, and it will check that all
conversion output produced by this converter are actually instances of
`RT`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Converter<RS, RT> cast<RS, RT>() => Converter.castFrom<S, T, RS, RT>(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Converter/cast.html>
:::
