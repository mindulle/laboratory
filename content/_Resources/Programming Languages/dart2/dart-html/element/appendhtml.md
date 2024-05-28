[dart:html](../../dart-html/dart-html-library){._links-link}

appendHtml method
=================

::: {.section .multi-line-signature}
void appendHtml(

1.  [String](../../dart-core/string-class) text,
2.  {[NodeValidator](../nodevalidator-class)? validator,
3.  [NodeTreeSanitizer](../nodetreesanitizer-class)? treeSanitizer}

)
:::

Parses the specified text as HTML and adds the resulting node after the
last child of this element.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void appendHtml(String text,
    {NodeValidator? validator, NodeTreeSanitizer? treeSanitizer}) {
  this.insertAdjacentHtml('beforeend', text,
      validator: validator, treeSanitizer: treeSanitizer);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/appendHtml.html>
:::
