[dart:svg](../../dart-svg/dart-svg-library){._links-link}

remove method
=============

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) remove(

1.  [Object](../../dart-core/object-class)? value

)

::: {.features}
inherited
:::
:::

Remove the class `value` from element, and return true on successful
removal.

This is the Dart equivalent of jQuery\'s
[removeClass](http://api.jquery.com/removeClass/).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool remove(Object? value) {
  if (value is! String) return false;
  _validateToken(value);
  Set<String> s = readClasses();
  bool result = s.remove(value);
  writeClasses(s);
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/AttributeClassSet/remove.html>
:::
