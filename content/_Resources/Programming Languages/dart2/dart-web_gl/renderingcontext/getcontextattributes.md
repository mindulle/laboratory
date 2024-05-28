[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

getContextAttributes method
===========================

::: {.section .multi-line-signature}
<div>

1.  \@Creates(\'ContextAttributes\|Null\')

</div>

[Map](../../dart-core/map-class)? getContextAttributes()

::: {.features}
\@Creates(\'ContextAttributes\|Null\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Creates('ContextAttributes|Null')
Map? getContextAttributes() {
  return convertNativeToDart_Dictionary(_getContextAttributes_1());
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext/getContextAttributes.html>
:::
