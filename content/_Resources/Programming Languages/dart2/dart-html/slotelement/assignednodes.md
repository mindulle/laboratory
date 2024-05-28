[dart:html](../../dart-html/dart-html-library){._links-link}

assignedNodes method
====================

::: {.section .multi-line-signature}
[List](../../dart-core/list-class)\<[Node](../node-class)\>
assignedNodes(

1.  \[[Map](../../dart-core/map-class)? options\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<Node> assignedNodes([Map? options]) {
  if (options != null) {
    var options_1 = convertDartToNative_Dictionary(options);
    return _assignedNodes_1(options_1);
  }
  return _assignedNodes_2();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SlotElement/assignedNodes.html>
:::
