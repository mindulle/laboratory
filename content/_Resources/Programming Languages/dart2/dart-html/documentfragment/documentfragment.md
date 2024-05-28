[dart:html](../../dart-html/dart-html-library){._links-link}

DocumentFragment.html constructor
=================================

::: {.section .multi-line-signature}
DocumentFragment.html(

1.  [String](../../dart-core/string-class)? html,
2.  {[NodeValidator](../nodevalidator-class)? validator,
3.  [NodeTreeSanitizer](../nodetreesanitizer-class)? treeSanitizer}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory DocumentFragment.html(String? html,
    {NodeValidator? validator, NodeTreeSanitizer? treeSanitizer}) {
  return document.body!.createFragment(html,
      validator: validator, treeSanitizer: treeSanitizer);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DocumentFragment/DocumentFragment.html.html>
:::
