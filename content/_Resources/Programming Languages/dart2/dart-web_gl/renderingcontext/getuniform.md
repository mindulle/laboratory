[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

getUniform method
=================

::: {.section .multi-line-signature}
<div>

1.  \@Creates(\'Null\|num\|String\|bool\|JSExtendableArray\|NativeFloat32List\|NativeInt32List\|NativeUint32List\')
2.  \@Returns(\'Null\|num\|String\|bool\|JSExtendableArray\|NativeFloat32List\|NativeInt32List\|NativeUint32List\')

</div>

[Object](../../dart-core/object-class)? getUniform(

1.  [Program](../program-class) program,
2.  [UniformLocation](../uniformlocation-class) location

)

::: {.features}
\@Creates(\'Null\|num\|String\|bool\|JSExtendableArray\|NativeFloat32List\|NativeInt32List\|NativeUint32List\'),
\@Returns(\'Null\|num\|String\|bool\|JSExtendableArray\|NativeFloat32List\|NativeInt32List\|NativeUint32List\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Creates(
    'Null|num|String|bool|JSExtendableArray|NativeFloat32List|NativeInt32List|NativeUint32List')
@Returns(
    'Null|num|String|bool|JSExtendableArray|NativeFloat32List|NativeInt32List|NativeUint32List')
Object? getUniform(Program program, UniformLocation location) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext/getUniform.html>
:::
