[dart:html](../../dart-html/dart-html-library){._links-link}

Element.html constructor
========================

::: {.section .multi-line-signature}
Element.html(

1.  [String](../../dart-core/string-class)? html,
2.  {[NodeValidator](../nodevalidator-class)? validator,
3.  [NodeTreeSanitizer](../nodetreesanitizer-class)? treeSanitizer}

)
:::

Creates an HTML element from a valid fragment of HTML.

``` {.language-dart data-language="dart"}
var element = new Element.html('<div class="foo">content</div>');
```

The HTML fragment should contain only one single root element, any
leading or trailing text nodes will be removed.

The HTML fragment is parsed as if it occurred within the context of a
`<body>` tag, this means that special elements such as `<caption>` which
must be parsed within the scope of a `<table>` element will be dropped.
Use [createFragment](createfragment) to parse contextual HTML fragments.

Unless a validator is provided this will perform the default validation
and remove all scriptable elements and attributes.

See also:

-   [NodeValidator](../nodevalidator-class)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Element.html(String? html,
    {NodeValidator? validator, NodeTreeSanitizer? treeSanitizer}) {
  var fragment = document.body!.createFragment(html,
      validator: validator, treeSanitizer: treeSanitizer);

  return fragment.nodes.where((e) => e is Element).single as Element;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/Element.html.html>
:::
