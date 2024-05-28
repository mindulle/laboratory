[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

getProgramParameter method
==========================

::: {.section .multi-line-signature}
<div>

1.  \@Creates(\'int\|bool\|Null\')
2.  \@Returns(\'int\|bool\|Null\')

</div>

[Object](../../dart-core/object-class)? getProgramParameter(

1.  [Program](../program-class) program,
2.  [int](../../dart-core/int-class) pname

)

::: {.features}
\@Creates(\'int\|bool\|Null\'), \@Returns(\'int\|bool\|Null\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Creates('int|bool|Null')
@Returns('int|bool|Null')
Object? getProgramParameter(Program program, int pname) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext/getProgramParameter.html>
:::
