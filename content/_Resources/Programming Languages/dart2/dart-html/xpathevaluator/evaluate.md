[dart:html](../../dart-html/dart-html-library){._links-link}

evaluate method
===============

::: {.section .multi-line-signature}
[XPathResult](../xpathresult-class) evaluate(

1.  [String](../../dart-core/string-class) expression,
2.  [Node](../node-class) contextNode,
3.  [XPathNSResolver](../xpathnsresolver-class)? resolver,
4.  \[[int](../../dart-core/int-class)? type,
5.  [Object](../../dart-core/object-class)? inResult\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
XPathResult evaluate(
    String expression, Node contextNode, XPathNSResolver? resolver,
    [int? type, Object? inResult]) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/XPathEvaluator/evaluate.html>
:::
