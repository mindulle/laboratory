[dart:svg](../../dart-svg/dart-svg-library){._links-link}

SvgElement.tag constructor
==========================

::: {.section .multi-line-signature}
SvgElement.tag(

1.  [String](../../dart-core/string-class) tag

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory SvgElement.tag(String tag) =>
    document.createElementNS("http://www.w3.org/2000/svg", tag) as SvgElement;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/SvgElement/SvgElement.tag.html>
:::
