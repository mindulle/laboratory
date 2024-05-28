[dart:convert](../../dart-convert/dart-convert-library){._links-link}

addSlice method
===============

::: {.section .multi-line-signature}
void addSlice(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    chunk,
2.  [int](../../dart-core/int-class) start,
3.  [int](../../dart-core/int-class) end,
4.  [bool](../../dart-core/bool-class) isLast

)
:::

Adds the next `chunk` to `this`.

Adds the bytes defined by `start` and `end`-exclusive to `this`.

If `isLast` is `true` closes `this`.

Contrary to `add` the given `chunk` must not be held onto. Once the
method returns, it is safe to overwrite the data in it.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addSlice(List<int> chunk, int start, int end, bool isLast);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/ByteConversionSink/addSlice.html>
:::
