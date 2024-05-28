[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

uniformMatrix2fv2 method
========================

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'uniformMatrix2fv\')

</div>

void uniformMatrix2fv2(

1.  [UniformLocation](../uniformlocation-class)? location,
2.  [bool](../../dart-core/bool-class) transpose,
3.  dynamic array,
4.  [int](../../dart-core/int-class) srcOffset,
5.  \[[int](../../dart-core/int-class)? srcLength\]

)

::: {.features}
\@JSName(\'uniformMatrix2fv\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('uniformMatrix2fv')
void uniformMatrix2fv2(
    UniformLocation? location, bool transpose, array, int srcOffset,
    [int? srcLength]) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext2/uniformMatrix2fv2.html>
:::
