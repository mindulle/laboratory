[dart:html](../../dart-html/dart-html-library){._links-link}

getRootNode method
==================

::: {.section .multi-line-signature}
[Node](../node-class) getRootNode(

1.  \[[Map](../../dart-core/map-class)? options\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Node getRootNode([Map? options]) {
  if (options != null) {
    var options_1 = convertDartToNative_Dictionary(options);
    return _getRootNode_1(options_1);
  }
  return _getRootNode_2();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Node/getRootNode.html>
:::
