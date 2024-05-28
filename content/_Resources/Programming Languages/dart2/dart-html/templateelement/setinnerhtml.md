[dart:html](../../dart-html/dart-html-library){._links-link}

setInnerHtml method
===================

::: {.section .multi-line-signature}
void setInnerHtml(

1.  [String](../../dart-core/string-class)? html,
2.  {[NodeValidator](../nodevalidator-class)? validator,
3.  [NodeTreeSanitizer](../nodetreesanitizer-class)? treeSanitizer}

)

::: {.features}
override
:::
:::

An override to place the contents into content rather than as child
nodes.

See also:

-   [w3c.github.io/DOM-Parsing/\#the-innerhtml-mixin](https://w3c.github.io/DOM-Parsing/#the-innerhtml-mixin)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void setInnerHtml(String? html,
    {NodeValidator? validator, NodeTreeSanitizer? treeSanitizer}) {
  text = null;
  content!.nodes.clear();
  var fragment = createFragment(html,
      validator: validator, treeSanitizer: treeSanitizer);

  content!.append(fragment);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/TemplateElement/setInnerHtml.html>
:::
