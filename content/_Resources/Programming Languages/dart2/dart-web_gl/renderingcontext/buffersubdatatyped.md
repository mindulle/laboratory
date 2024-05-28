[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

bufferSubDataTyped method
=========================

::: {.section .multi-line-signature}
<div>

1.  @[Deprecated](../../dart-core/deprecated-class)(\"Use
    bufferSubData\")

</div>

void bufferSubDataTyped(

1.  [int](../../dart-core/int-class) target,
2.  [int](../../dart-core/int-class) offset,
3.  [TypedData](../../dart-typed_data/typeddata-class) data

)

::: {.features}
@[Deprecated](../../dart-core/deprecated-class)(\"Use bufferSubData\")
:::
:::

Set the bufferSubData to `data`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Deprecated("Use bufferSubData")
void bufferSubDataTyped(int target, int offset, TypedData data) {
  bufferSubData(target, offset, data);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext/bufferSubDataTyped.html>
:::
