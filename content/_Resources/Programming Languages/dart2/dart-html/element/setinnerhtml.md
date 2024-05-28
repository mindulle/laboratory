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

Parses the HTML fragment and sets it as the contents of this element.
This ensures that the generated content follows the sanitization rules
specified by the validator or treeSanitizer.

If the default validation behavior is too restrictive then a new
NodeValidator should be created, either extending or wrapping a default
validator and overriding the validation APIs.

The treeSanitizer is used to walk the generated node tree and sanitize
it. A custom treeSanitizer can also be provided to perform special
validation rules but since the API is more complex to implement this is
discouraged.

The resulting tree is guaranteed to only contain nodes and attributes
which are allowed by the provided validator.

See also:

-   [NodeValidator](../nodevalidator-class)
-   [NodeTreeSanitizer](../nodetreesanitizer-class)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void setInnerHtml(String? html,
    {NodeValidator? validator, NodeTreeSanitizer? treeSanitizer}) {
  text = null;
  if (treeSanitizer is _TrustedHtmlTreeSanitizer) {
    _innerHtml = html;
  } else {
    append(createFragment(html,
        validator: validator, treeSanitizer: treeSanitizer));
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/setInnerHtml.html>
:::
