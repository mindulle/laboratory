[dart:html](../../dart-html/dart-html-library){._links-link}

DocumentFragment.svg constructor
================================

::: {.section .multi-line-signature}
DocumentFragment.svg(

1.  [String](../../dart-core/string-class)? svgContent,
2.  {[NodeValidator](../nodevalidator-class)? validator,
3.  [NodeTreeSanitizer](../nodetreesanitizer-class)? treeSanitizer}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory DocumentFragment.svg(String? svgContent,
    {NodeValidator? validator, NodeTreeSanitizer? treeSanitizer}) {
  return new svg.SvgSvgElement().createFragment(svgContent,
      validator: validator, treeSanitizer: treeSanitizer);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DocumentFragment/DocumentFragment.svg.html>
:::
