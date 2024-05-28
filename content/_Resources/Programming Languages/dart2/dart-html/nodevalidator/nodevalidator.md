[dart:html](../../dart-html/dart-html-library){._links-link}

NodeValidator constructor
=========================

::: {.section .multi-line-signature}
NodeValidator(

1.  {[UriPolicy](../uripolicy-class)? uriPolicy}

)
:::

Construct a default NodeValidator which only accepts whitelisted HTML5
elements and attributes.

If a uriPolicy is not specified then the default uriPolicy will be used.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory NodeValidator({UriPolicy? uriPolicy}) =>
    new _Html5NodeValidator(uriPolicy: uriPolicy);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/NodeValidator/NodeValidator.html>
:::
