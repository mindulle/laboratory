[dart:core](../../dart-core/dart-core-library){._links-link}

indexOf method
==============

::: {.section .multi-line-signature}
[int](../int-class) indexOf(

1.  E element,
2.  \[[int](../int-class) start = 0\]

)
:::

The first index of `element` in this list.

Searches the list from index `start` to the end of the list. The first
time an object `o` is encountered so that `o == element`, the index of
`o` is returned.

``` {.language-dart data-language="dart"}
final notes = <String>['do', 're', 'mi', 're'];
print(notes.indexOf('re')); // 1

final indexWithStart = notes.indexOf('re', 2); // 3
```

Returns -1 if `element` is not found.

``` {.language-dart data-language="dart"}
final notes = <String>['do', 're', 'mi', 're'];
final index = notes.indexOf('fa'); // -1
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int indexOf(E element, [int start = 0]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/indexOf.html>
:::
