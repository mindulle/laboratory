[dart:svg](../../dart-svg/dart-svg-library){._links-link}

every method
============

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) every(

1.  [bool](../../dart-core/bool-class) f(
    1.  [String](../../dart-core/string-class) element

    )

)

::: {.features}
inherited
:::
:::

Checks whether every element of this iterable satisfies `test`.

Checks every element in iteration order, and returns `false` if any of
them make `test` return `false`, otherwise returns `true`.

Example:

``` {.language-dart data-language="dart"}
final planetsByMass = <double, String>{0.06: 'Mercury', 0.81: 'Venus',
  0.11: 'Mars'};
// Checks whether all keys are smaller than 1.
final every = planetsByMass.keys.every((key) => key < 1.0); // true
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool every(bool f(String element)) => readClasses().every(f);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/AttributeClassSet/every.html>
:::
