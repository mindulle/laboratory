[dart:html](../../dart-html/dart-html-library){._links-link}

toggle method
=============

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) toggle(

1.  [String](../../dart-core/string-class) value,
2.  \[[bool](../../dart-core/bool-class)? shouldAdd\]

)
:::

Adds the class `value` to the element if it is not on it, removes it if
it is.

If `shouldAdd` is true, then we always add that `value` to the element.
If `shouldAdd` is false then we always remove `value` from the element.

If this corresponds to one element, returns `true` if `value` is present
after the operation, and returns `false` if `value` is absent after the
operation.

If this CssClassSet corresponds to many elements, `false` is always
returned.

`value` must be a valid \'token\' representing a single class, i.e. a
non-empty string containing no whitespace. To toggle multiple classes,
use [toggleAll](toggleall).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool toggle(String value, [bool? shouldAdd]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssClassSet/toggle.html>
:::
