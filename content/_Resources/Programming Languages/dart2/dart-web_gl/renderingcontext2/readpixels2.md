[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

readPixels2 method
==================

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'readPixels\')

</div>

void readPixels2(

1.  [int](../../dart-core/int-class) x,
2.  [int](../../dart-core/int-class) y,
3.  [int](../../dart-core/int-class) width,
4.  [int](../../dart-core/int-class) height,
5.  [int](../../dart-core/int-class) format,
6.  [int](../../dart-core/int-class) type,
7.  dynamic dstData\_OR\_offset,
8.  \[[int](../../dart-core/int-class)? offset\]

)

::: {.features}
\@JSName(\'readPixels\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('readPixels')
void readPixels2(int x, int y, int width, int height, int format, int type,
    dstData_OR_offset,
    [int? offset]) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext2/readPixels2.html>
:::
