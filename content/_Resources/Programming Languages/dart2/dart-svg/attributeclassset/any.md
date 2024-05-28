[dart:svg](../../dart-svg/dart-svg-library){._links-link}

any method
==========

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) any(

1.  [bool](../../dart-core/bool-class) f(
    1.  [String](../../dart-core/string-class) element

    )

)

::: {.features}
inherited
:::
:::

Checks whether any element of this iterable satisfies `test`.

Checks every element in iteration order, and returns `true` if any of
them make `test` return `true`, otherwise returns false.

Example:

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3, 5, 6, 7];
var result = numbers.any((element) => element >= 5); // true;
result = numbers.any((element) => element >= 10); // false;
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool any(bool f(String element)) => readClasses().any(f);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/AttributeClassSet/any.html>
:::
