[dart:svg](../../dart-svg/dart-svg-library){._links-link}

createFragment method
=====================

::: {.section .multi-line-signature}
[DocumentFragment](../../dart-html/documentfragment-class)
createFragment(

1.  [String](../../dart-core/string-class)? svg,
2.  {[NodeValidator](../../dart-html/nodevalidator-class)? validator,
3.  [NodeTreeSanitizer](../../dart-html/nodetreesanitizer-class)?
    treeSanitizer}

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

-   [NodeValidator](../../dart-html/nodevalidator-class)
-   [NodeTreeSanitizer](../../dart-html/nodetreesanitizer-class)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
DocumentFragment createFragment(String? svg,
    {NodeValidator? validator, NodeTreeSanitizer? treeSanitizer}) {
  if (treeSanitizer == null) {
    if (validator == null) {
      validator = new NodeValidatorBuilder.common()..allowSvg();
    }
    treeSanitizer = new NodeTreeSanitizer(validator);
  }

  // We create a fragment which will parse in the HTML parser
  var html = '<svg version="1.1">$svg</svg>';
  var fragment =
      document.body!.createFragment(html, treeSanitizer: treeSanitizer);

  var svgFragment = new DocumentFragment();
  // The root is the <svg/> element, need to pull out the contents.
  var root = fragment.nodes.single;
  while (root.firstChild != null) {
    svgFragment.append(root.firstChild!);
  }
  return svgFragment;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/SvgElement/createFragment.html>
:::
