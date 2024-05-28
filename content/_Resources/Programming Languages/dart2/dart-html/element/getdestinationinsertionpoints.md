[dart:html](../../dart-html/dart-html-library){._links-link}

getDestinationInsertionPoints method
====================================

::: {.section .multi-line-signature}
<div>

1.  \@Returns(\'NodeList\')
2.  \@Creates(\'NodeList\')

</div>

[List](../../dart-core/list-class)\<[Node](../node-class)\>
getDestinationInsertionPoints()

::: {.features}
\@Returns(\'NodeList\'), \@Creates(\'NodeList\')
:::
:::

Returns a list of shadow DOM insertion points to which this element is
distributed.

Other resources
---------------

-   [Shadow DOM
    specification](https://dvcs.w3.org/hg/webcomponents/raw-file/tip/spec/shadow/index.html)
    from W3C.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Returns('NodeList')
@Creates('NodeList')
List<Node> getDestinationInsertionPoints() native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/getDestinationInsertionPoints.html>
:::
