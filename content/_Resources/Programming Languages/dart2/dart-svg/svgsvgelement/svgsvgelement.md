[dart:svg](../../dart-svg/dart-svg-library){._links-link}

SvgSvgElement constructor
=========================

::: {.section .multi-line-signature}
SvgSvgElement()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory SvgSvgElement() {
  final el = new SvgElement.tag("svg");
  // The SVG spec requires the version attribute to match the spec version
  el.attributes['version'] = "1.1";
  return el as SvgSvgElement;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/SvgSvgElement/SvgSvgElement.html>
:::
