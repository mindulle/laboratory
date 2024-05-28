[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

bufferDataTyped method
======================

::: {.section .multi-line-signature}
<div>

1.  @[Deprecated](../../dart-core/deprecated-class)(\"Use bufferData\")

</div>

void bufferDataTyped(

1.  [int](../../dart-core/int-class) target,
2.  [TypedData](../../dart-typed_data/typeddata-class) data,
3.  [int](../../dart-core/int-class) usage

)

::: {.features}
@[Deprecated](../../dart-core/deprecated-class)(\"Use bufferData\")
:::
:::

Set the bufferData to `data`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Deprecated("Use bufferData")
void bufferDataTyped(int target, TypedData data, int usage) {
  bufferData(target, data, usage);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext/bufferDataTyped.html>
:::
