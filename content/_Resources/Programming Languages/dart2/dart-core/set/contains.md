[dart:core](../../dart-core/dart-core-library){._links-link}

contains method
===============

::: {.section .multi-line-signature}
[bool](../bool-class) contains(

1.  [Object](../object-class)? value

)

::: {.features}
override
:::
:::

Whether `value` is in the set.

``` {.language-dart data-language="dart"}
final characters = <String>{'A', 'B', 'C'};
final containsB = characters.contains('B'); // true
final containsD = characters.contains('D'); // false
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool contains(Object? value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Set/contains.html>
:::
