[dart:convert](../../dart-convert/dart-convert-library){._links-link}

fuse\<T\> method
================

::: {.section .multi-line-signature}
[Converter](../converter-class)\<[List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>,
T\> fuse\<T\>(

1.  [Converter](../converter-class)\<[String](../../dart-core/string-class),
    T\> next

)

::: {.features}
override
:::
:::

Fuses `this` with `other`.

Encoding with the resulting converter is equivalent to converting with
`this` before converting with `other`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external Converter<List<int>, T> fuse<T>(Converter<String, T> next);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Utf8Decoder/fuse.html>
:::
