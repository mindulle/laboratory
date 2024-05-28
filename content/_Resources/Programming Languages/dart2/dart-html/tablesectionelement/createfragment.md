[dart:html](../../dart-html/dart-html-library){._links-link}

createFragment method
=====================

::: {.section .multi-line-signature}
[DocumentFragment](../documentfragment-class) createFragment(

1.  [String](../../dart-core/string-class)? html,
2.  {[NodeValidator](../nodevalidator-class)? validator,
3.  [NodeTreeSanitizer](../nodetreesanitizer-class)? treeSanitizer}

)

::: {.features}
override
:::
:::

Create a DocumentFragment from the HTML fragment and ensure that it
follows the sanitization rules specified by the validator or
treeSanitizer.

If the default validation behavior is too restrictive then a new
NodeValidator should be created, either extending or wrapping a default
validator and overriding the validation APIs.

The treeSanitizer is used to walk the generated node tree and sanitize
it. A custom treeSanitizer can also be provided to perform special
validation rules but since the API is more complex to implement this is
discouraged.

The returned tree is guaranteed to only contain nodes and attributes
which are allowed by the provided validator.

See also:

-   [NodeValidator](../nodevalidator-class)
-   [NodeTreeSanitizer](../nodetreesanitizer-class)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
DocumentFragment createFragment(String? html,
    {NodeValidator? validator, NodeTreeSanitizer? treeSanitizer}) {
  if (Range.supportsCreateContextualFragment) {
    return super.createFragment(html,
        validator: validator, treeSanitizer: treeSanitizer);
  }
  // IE9 workaround which does not support innerHTML on Table elements.
  var fragment = new DocumentFragment();
  var section = new TableElement()
      .createFragment(html,
          validator: validator, treeSanitizer: treeSanitizer)
      .nodes
      .single;
  fragment.nodes.addAll(section.nodes);
  return fragment;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/TableSectionElement/createFragment.html>
:::
