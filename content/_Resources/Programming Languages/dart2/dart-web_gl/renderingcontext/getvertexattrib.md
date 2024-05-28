[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

getVertexAttrib method
======================

::: {.section .multi-line-signature}
<div>

1.  \@Creates(\'Null\|num\|bool\|NativeFloat32List\|Buffer\')
2.  \@Returns(\'Null\|num\|bool\|NativeFloat32List\|Buffer\')

</div>

[Object](../../dart-core/object-class)? getVertexAttrib(

1.  [int](../../dart-core/int-class) index,
2.  [int](../../dart-core/int-class) pname

)

::: {.features}
\@Creates(\'Null\|num\|bool\|NativeFloat32List\|Buffer\'),
\@Returns(\'Null\|num\|bool\|NativeFloat32List\|Buffer\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Creates('Null|num|bool|NativeFloat32List|Buffer')
@Returns('Null|num|bool|NativeFloat32List|Buffer')
Object? getVertexAttrib(int index, int pname) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext/getVertexAttrib.html>
:::
