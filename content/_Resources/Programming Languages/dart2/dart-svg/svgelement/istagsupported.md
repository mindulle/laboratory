[dart:svg](../../dart-svg/dart-svg-library){._links-link}

isTagSupported method
=====================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) isTagSupported(

1.  [String](../../dart-core/string-class) tag

)

::: {.features}
override
:::
:::

Checks to see if the SVG element type is supported by the current
platform.

The tag should be a valid SVG element tag name.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static bool isTagSupported(String tag) {
  var e = new SvgElement.tag(tag);
  return e is SvgElement && !(e is UnknownElement);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/SvgElement/isTagSupported.html>
:::
