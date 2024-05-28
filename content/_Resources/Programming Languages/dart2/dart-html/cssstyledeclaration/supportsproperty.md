[dart:html](../../dart-html/dart-html-library){._links-link}

supportsProperty method
=======================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) supportsProperty(

1.  [String](../../dart-core/string-class) propertyName

)
:::

Returns true if the provided *CSS* property name is supported on this
element.

Please note the property name camelCase, not-hyphens. This method
returns true if the property is accessible via an unprefixed *or*
prefixed property.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool supportsProperty(String propertyName) {
  return _supportsProperty(propertyName) ||
      _supportsProperty(_camelCase("${Device.cssPrefix}$propertyName"));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssStyleDeclaration/supportsProperty.html>
:::
