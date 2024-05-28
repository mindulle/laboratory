[dart:svg](../../dart-svg/dart-svg-library){._links-link}

add method
==========

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) add(

1.  [String](../../dart-core/string-class) value

)

::: {.features}
inherited
:::
:::

Add the class `value` to element.

This is the Dart equivalent of jQuery\'s
[addClass](http://api.jquery.com/addClass/).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool add(String value) {
  _validateToken(value);
  // TODO - figure out if we need to do any validation here
  // or if the browser natively does enough.
  return modify((s) => s.add(value)) ?? false;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/AttributeClassSet/add.html>
:::
