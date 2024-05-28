[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

bufferSubData2 method
=====================

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'bufferSubData\')

</div>

void bufferSubData2(

1.  [int](../../dart-core/int-class) target,
2.  [int](../../dart-core/int-class) dstByteOffset,
3.  [TypedData](../../dart-typed_data/typeddata-class) srcData,
4.  [int](../../dart-core/int-class) srcOffset,
5.  \[[int](../../dart-core/int-class)? length\]

)

::: {.features}
\@JSName(\'bufferSubData\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('bufferSubData')
void bufferSubData2(
    int target, int dstByteOffset, TypedData srcData, int srcOffset,
    [int? length]) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext2/bufferSubData2.html>
:::
