[dart:html](../../dart-html/dart-html-library){._links-link}

supportsPointConversions property
=================================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) supportsPointConversions
:::

convertPointFromNodeToPage and convertPointFromPageToNode are removed.
see <http://dev.w3.org/csswg/cssom-view/#geometry>

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static bool get supportsPointConversions => DomPoint.supported;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/supportsPointConversions.html>
:::
