[dart:core](../../dart-core/dart-core-library){._links-link}

clear method
============

::: {.section .multi-line-signature}
void clear()
:::

Removes all objects from this list; the length of the list becomes zero.

The list must be growable.

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3];
numbers.clear();
print(numbers.length); // 0
print(numbers); // []
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void clear();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/clear.html>
:::
