[dart:svg](../../dart-svg/dart-svg-library){._links-link}

contains method
===============

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) contains(

1.  [Object](../../dart-core/object-class)? value

)

::: {.features}
inherited
:::
:::

Determine if this element contains the class `value`.

This is the Dart equivalent of jQuery\'s
[hasClass](http://api.jquery.com/hasClass/).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool contains(Object? value) {
  if (value is! String) return false;
  _validateToken(value);
  return readClasses().contains(value);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/AttributeClassSet/contains.html>
:::
