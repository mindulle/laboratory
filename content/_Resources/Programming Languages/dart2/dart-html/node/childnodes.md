[dart:html](../../dart-html/dart-html-library){._links-link}

childNodes property
===================

::: {#getter .section .multi-line-signature}
[List](../../dart-core/list-class)\<[Node](../node-class)\> childNodes

::: {.features}
\@Returns(\'NodeList\'), \@Creates(\'NodeList\')
:::
:::

A list of this node\'s children.

Other resources
---------------

-   [Node.childNodes](https://developer.mozilla.org/en-US/docs/Web/API/Node.childNodes)
    from MDN.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Returns('NodeList')
@Creates('NodeList')
List<Node> get childNodes native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Node/childNodes.html>
:::
