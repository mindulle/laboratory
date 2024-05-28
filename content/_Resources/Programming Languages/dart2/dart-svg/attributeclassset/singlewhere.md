[dart:svg](../../dart-svg/dart-svg-library){._links-link}

singleWhere method
==================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) singleWhere(

1.  [bool](../../dart-core/bool-class) test(
    1.  [String](../../dart-core/string-class) value

    ),
2.  {[String](../../dart-core/string-class) orElse( )?}

)

::: {.features}
inherited
:::
:::

Returns the single element that satisfies `test`.

Checks elements to see if `test(element)` returns true. If exactly one
element satisfies `test`, that element is returned. If more than one
matching element is found, throws
[StateError](../../dart-core/stateerror-class). If no matching element
is found, returns the result of `orElse`. If `orElse` is omitted, it
defaults to throwing a [StateError](../../dart-core/stateerror-class).

Example:

``` {.language-dart data-language="dart"}
final numbers = <int>[2, 2, 10];
var result = numbers.singleWhere((element) => element > 5); // 10
```

When no matching element is found, the result of calling `orElse` is
returned instead.

``` {.language-dart data-language="dart"}
result = numbers.singleWhere((element) => element == 1,
    orElse: () => -1); // -1
```

There must not be more than one matching element.

``` {.language-dart data-language="dart"}
result = numbers.singleWhere((element) => element == 2); // Throws Error.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String singleWhere(bool test(String value), {String orElse()?}) =>
    readClasses().singleWhere(test, orElse: orElse);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/AttributeClassSet/singleWhere.html>
:::
