[dart:svg](../../dart-svg/dart-svg-library){._links-link}

toggle method
=============

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) toggle(

1.  [String](../../dart-core/string-class) value,
2.  \[[bool](../../dart-core/bool-class)? shouldAdd\]

)

::: {.features}
inherited
:::
:::

Adds the class `value` to the element if it is not on it, removes it if
it is.

If `shouldAdd` is true, then we always add that `value` to the element.
If `shouldAdd` is false then we always remove `value` from the element.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool toggle(String value, [bool? shouldAdd]) {
  _validateToken(value);
  Set<String> s = readClasses();
  bool result = false;
  if (shouldAdd == null) shouldAdd = !s.contains(value);
  if (shouldAdd) {
    s.add(value);
    result = true;
  } else {
    s.remove(value);
  }
  writeClasses(s);
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/AttributeClassSet/toggle.html>
:::
