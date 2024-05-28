[dart:core](../../dart-core/dart-core-library){._links-link}

operator == method
==================

::: {.section .multi-line-signature}
[bool](../bool-class) operator ==(

1.  [Object](../object-class) other

)

::: {.features}
override
:::
:::

Whether `other` is a `String` with the same sequence of code units.

This method compares each individual code unit of the strings. It does
not check for Unicode equivalence. For example, both the following
strings represent the string \'Amélie\', but due to their different
encoding, are not equal:

``` {.language-dart data-language="dart"}
'Am\xe9lie' == 'Ame\u{301}lie'; // false
```

The first string encodes \'é\' as a single unicode code unit (also a
single rune), whereas the second string encodes it as \'e\' with the
combining accent character \'◌́\'.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool operator ==(Object other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/operator_equals.html>
:::
