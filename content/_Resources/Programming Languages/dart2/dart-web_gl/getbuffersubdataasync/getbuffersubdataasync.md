[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

getBufferSubDataAsync method
============================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) getBufferSubDataAsync(

1.  [int](../../dart-core/int-class) target,
2.  [int](../../dart-core/int-class) srcByteOffset,
3.  [TypedData](../../dart-typed_data/typeddata-class) dstData,
4.  \[[int](../../dart-core/int-class)? dstOffset,
5.  [int](../../dart-core/int-class)? length\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future getBufferSubDataAsync(int target, int srcByteOffset, TypedData dstData,
        [int? dstOffset, int? length]) =>
    promiseToFuture(JS("", "#.getBufferSubDataAsync(#, #, #, #, #)", this,
        target, srcByteOffset, dstData, dstOffset, length));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/GetBufferSubDataAsync/getBufferSubDataAsync.html>
:::
