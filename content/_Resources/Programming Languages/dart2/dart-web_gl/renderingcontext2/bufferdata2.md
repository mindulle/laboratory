[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

bufferData2 method
==================

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'bufferData\')

</div>

void bufferData2(

1.  [int](../../dart-core/int-class) target,
2.  [TypedData](../../dart-typed_data/typeddata-class) srcData,
3.  [int](../../dart-core/int-class) usage,
4.  [int](../../dart-core/int-class) srcOffset,
5.  \[[int](../../dart-core/int-class)? length\]

)

::: {.features}
\@JSName(\'bufferData\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('bufferData')
void bufferData2(int target, TypedData srcData, int usage, int srcOffset,
    [int? length]) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext2/bufferData2.html>
:::
