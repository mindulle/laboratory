[dart:html](../../dart-html/dart-html-library){._links-link}

initMutationEvent method
========================

::: {.section .multi-line-signature}
void initMutationEvent(

1.  [String](../../dart-core/string-class)? type,
2.  [bool](../../dart-core/bool-class)? bubbles,
3.  [bool](../../dart-core/bool-class)? cancelable,
4.  [Node](../node-class)? relatedNode,
5.  [String](../../dart-core/string-class)? prevValue,
6.  [String](../../dart-core/string-class)? newValue,
7.  [String](../../dart-core/string-class)? attrName,
8.  [int](../../dart-core/int-class)? attrChange

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void initMutationEvent(
    String? type,
    bool? bubbles,
    bool? cancelable,
    Node? relatedNode,
    String? prevValue,
    String? newValue,
    String? attrName,
    int? attrChange) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MutationEvent/initMutationEvent.html>
:::
