[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

getParameter method
===================

::: {.section .multi-line-signature}
<div>

1.  \@Creates(\'Null\|num\|String\|bool\|JSExtendableArray\|NativeFloat32List\|NativeInt32List\|NativeUint32List\|Framebuffer\|Renderbuffer\|Texture\')
2.  \@Returns(\'Null\|num\|String\|bool\|JSExtendableArray\|NativeFloat32List\|NativeInt32List\|NativeUint32List\|Framebuffer\|Renderbuffer\|Texture\')

</div>

[Object](../../dart-core/object-class)? getParameter(

1.  [int](../../dart-core/int-class) pname

)

::: {.features}
\@Creates(\'Null\|num\|String\|bool\|JSExtendableArray\|NativeFloat32List\|NativeInt32List\|NativeUint32List\|Framebuffer\|Renderbuffer\|Texture\'),
\@Returns(\'Null\|num\|String\|bool\|JSExtendableArray\|NativeFloat32List\|NativeInt32List\|NativeUint32List\|Framebuffer\|Renderbuffer\|Texture\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Creates(
    'Null|num|String|bool|JSExtendableArray|NativeFloat32List|NativeInt32List|NativeUint32List|Framebuffer|Renderbuffer|Texture')
@Returns(
    'Null|num|String|bool|JSExtendableArray|NativeFloat32List|NativeInt32List|NativeUint32List|Framebuffer|Renderbuffer|Texture')
Object? getParameter(int pname) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext/getParameter.html>
:::
