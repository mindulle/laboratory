[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

getFramebufferAttachmentParameter method
========================================

::: {.section .multi-line-signature}
<div>

1.  \@Creates(\'int\|Renderbuffer\|Texture\|Null\')
2.  \@Returns(\'int\|Renderbuffer\|Texture\|Null\')

</div>

[Object](../../dart-core/object-class)?
getFramebufferAttachmentParameter(

1.  [int](../../dart-core/int-class) target,
2.  [int](../../dart-core/int-class) attachment,
3.  [int](../../dart-core/int-class) pname

)

::: {.features}
\@Creates(\'int\|Renderbuffer\|Texture\|Null\'),
\@Returns(\'int\|Renderbuffer\|Texture\|Null\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Creates('int|Renderbuffer|Texture|Null')
@Returns('int|Renderbuffer|Texture|Null')
Object? getFramebufferAttachmentParameter(
    int target, int attachment, int pname) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext/getFramebufferAttachmentParameter.html>
:::
