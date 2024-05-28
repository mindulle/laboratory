[dart:collection](../../dart-collection/dart-collection-library){._links-link}

contains method
===============

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) contains(

1.  [Object](../../dart-core/object-class)? element

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
bool contains(Object? element) => _source.contains(element);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/UnmodifiableSetView/contains.html>
:::
