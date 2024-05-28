[dart:svg](../../dart-svg/dart-svg-library){._links-link}

SvgElement.svg constructor
==========================

::: {.section .multi-line-signature}
SvgElement.svg(

1.  [String](../../dart-core/string-class) svg,
2.  {[NodeValidator](../../dart-html/nodevalidator-class)? validator,
3.  [NodeTreeSanitizer](../../dart-html/nodetreesanitizer-class)?
    treeSanitizer}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory SvgElement.svg(String svg,
    {NodeValidator? validator, NodeTreeSanitizer? treeSanitizer}) {
  if (validator == null && treeSanitizer == null) {
    validator = new NodeValidatorBuilder.common()..allowSvg();
  }

  final match = _START_TAG_REGEXP.firstMatch(svg);
  var parentElement;
  if (match != null && match.group(1)!.toLowerCase() == 'svg') {
    parentElement = document.body;
  } else {
    parentElement = new SvgSvgElement();
  }
  var fragment = parentElement.createFragment(svg,
      validator: validator, treeSanitizer: treeSanitizer);
  return fragment.nodes.where((e) => e is SvgElement).single;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/SvgElement/SvgElement.svg.html>
:::
