[dart:convert](../../dart-convert/dart-convert-library){._links-link}

castFrom\<SS, ST, TS, TT\> method
=================================

::: {.section .multi-line-signature}
[Converter](../converter-class)\<TS, TT\> castFrom\<SS, ST, TS, TT\>(

1.  [Converter](../converter-class)\<SS, ST\> source

)

::: {.features}
override
:::
:::

Adapts `source` to be a `Converter<TS, TT>`.

This allows `source` to be used at the new type, but at run-time it must
satisfy the requirements of both the new type and its original type.

Conversion input must be both `SS` and `TS` and the output created by
`source` for those input must be both `ST` and `TT`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Converter<TS, TT> castFrom<SS, ST, TS, TT>(Converter<SS, ST> source) =>
    CastConverter<SS, ST, TS, TT>(source);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Converter/castFrom.html>
:::
