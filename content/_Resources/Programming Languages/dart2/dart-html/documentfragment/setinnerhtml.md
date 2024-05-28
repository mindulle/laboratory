[dart:html](../../dart-html/dart-html-library){._links-link}

setInnerHtml method
===================

::: {.section .multi-line-signature}
void setInnerHtml(

1.  [String](../../dart-core/string-class)? html,
2.  {[NodeValidator](../nodevalidator-class)? validator,
3.  [NodeTreeSanitizer](../nodetreesanitizer-class)? treeSanitizer}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void setInnerHtml(String? html,
    {NodeValidator? validator, NodeTreeSanitizer? treeSanitizer}) {
  this.nodes.clear();
  append(document.body!.createFragment(html,
      validator: validator, treeSanitizer: treeSanitizer));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DocumentFragment/setInnerHtml.html>
:::
