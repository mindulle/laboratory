[dart:html](../../dart-html/dart-html-library){._links-link}

insertAdjacentHtml method
=========================

::: {.section .multi-line-signature}
void insertAdjacentHtml(

1.  [String](../../dart-core/string-class) where,
2.  [String](../../dart-core/string-class) html,
3.  {[NodeValidator](../nodevalidator-class)? validator,
4.  [NodeTreeSanitizer](../nodetreesanitizer-class)? treeSanitizer}

)
:::

Parses text as an HTML fragment and inserts it into the DOM at the
specified location.

The `where` parameter indicates where to insert the HTML fragment:

-   \'beforeBegin\': Immediately before this element.
-   \'afterBegin\': As the first child of this element.
-   \'beforeEnd\': As the last child of this element.
-   \'afterEnd\': Immediately after this element.

``` {.language-dart data-language="dart"}
var html = '<div class="something">content</div>';
    // Inserts as the first child
    document.body.insertAdjacentHtml('afterBegin', html);
    var createdElement = document.body.children[0];
    print(createdElement.classes[0]); // Prints 'something'
```

See also:

-   [insertAdjacentText](insertadjacenttext)
-   [insertAdjacentElement](insertadjacentelement)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void insertAdjacentHtml(String where, String html,
    {NodeValidator? validator, NodeTreeSanitizer? treeSanitizer}) {
  if (treeSanitizer is _TrustedHtmlTreeSanitizer) {
    _insertAdjacentHtml(where, html);
  } else {
    _insertAdjacentNode(
        where,
        createFragment(html,
            validator: validator, treeSanitizer: treeSanitizer));
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/insertAdjacentHtml.html>
:::
