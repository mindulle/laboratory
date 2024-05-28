[dart:svg](../../dart-svg/dart-svg-library){._links-link}

getEnclosureList method
=======================

::: {.section .multi-line-signature}
<div>

1.  \@Returns(\'NodeList\')
2.  \@Creates(\'NodeList\')

</div>

[List](../../dart-core/list-class)\<[Node](../../dart-html/node-class)\>
getEnclosureList(

1.  [Rect](../rect-class) rect,
2.  [SvgElement](../svgelement-class)? referenceElement

)

::: {.features}
\@Returns(\'NodeList\'), \@Creates(\'NodeList\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Returns('NodeList')
@Creates('NodeList')
List<Node> getEnclosureList(Rect rect, SvgElement? referenceElement) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/SvgSvgElement/getEnclosureList.html>
:::
