[dart:html](../../dart-html/dart-html-library){._links-link}

append method
=============

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'appendChild\')

</div>

[Node](../node-class) append(

1.  [Node](../node-class) node

)

::: {.features}
\@JSName(\'appendChild\')
:::
:::

Adds a node to the end of the child [nodes](nodes) list of this node.

If the node already exists in this document, it will be removed from its
current parent node, then added to this node.

This method is more efficient than `nodes.add`, and is the preferred way
of appending a child node.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('appendChild')
/**
 * Adds a node to the end of the child [nodes] list of this node.
 *
 * If the node already exists in this document, it will be removed from its
 * current parent node, then added to this node.
 *
 * This method is more efficient than `nodes.add`, and is the preferred
 * way of appending a child node.
 */
Node append(Node node) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Node/append.html>
:::
