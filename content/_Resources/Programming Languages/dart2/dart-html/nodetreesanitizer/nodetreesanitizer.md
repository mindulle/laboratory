[dart:html](../../dart-html/dart-html-library){._links-link}

NodeTreeSanitizer constructor
=============================

::: {.section .multi-line-signature}
NodeTreeSanitizer(

1.  [NodeValidator](../nodevalidator-class) validator

)
:::

Constructs a default tree sanitizer which will remove all elements and
attributes which are not allowed by the provided validator.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory NodeTreeSanitizer(NodeValidator validator) =>
    new _ValidatingTreeSanitizer(validator);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/NodeTreeSanitizer/NodeTreeSanitizer.html>
:::
