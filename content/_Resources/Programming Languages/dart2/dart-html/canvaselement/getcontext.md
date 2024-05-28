[dart:html](../../dart-html/dart-html-library){._links-link}

getContext method
=================

::: {.section .multi-line-signature}
<div>

1.  \@Creates(\'CanvasRenderingContext2D\|RenderingContext\|RenderingContext2\')
2.  \@Returns(\'CanvasRenderingContext2D\|RenderingContext\|RenderingContext2\|Null\')

</div>

[Object](../../dart-core/object-class)? getContext(

1.  [String](../../dart-core/string-class) contextId,
2.  \[[Map](../../dart-core/map-class)? attributes\]

)

::: {.features}
\@Creates(\'CanvasRenderingContext2D\|RenderingContext\|RenderingContext2\'),
\@Returns(\'CanvasRenderingContext2D\|RenderingContext\|RenderingContext2\|Null\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Creates('CanvasRenderingContext2D|RenderingContext|RenderingContext2')
@Returns('CanvasRenderingContext2D|RenderingContext|RenderingContext2|Null')
Object? getContext(String contextId, [Map? attributes]) {
  if (attributes != null) {
    var attributes_1 = convertDartToNative_Dictionary(attributes);
    return _getContext_1(contextId, attributes_1);
  }
  return _getContext_2(contextId);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasElement/getContext.html>
:::
