[dart:core](../../dart-core/dart-core-library){._links-link}

indexWhere method
=================

::: {.section .multi-line-signature}
[int](../int-class) indexWhere(

1.  [bool](../bool-class) test(
    1.  E element

    ),
2.  \[[int](../int-class) start = 0\]

)
:::

The first index in the list that satisfies the provided `test`.

Searches the list from index `start` to the end of the list. The first
time an object `o` is encountered so that `test(o)` is true, the index
of `o` is returned.

``` {.language-dart data-language="dart"}
final notes = <String>['do', 're', 'mi', 're'];
final first = notes.indexWhere((note) => note.startsWith('r')); // 1
final second = notes.indexWhere((note) => note.startsWith('r'), 2); // 3
```

Returns -1 if `element` is not found.

``` {.language-dart data-language="dart"}
final notes = <String>['do', 're', 'mi', 're'];
final index = notes.indexWhere((note) => note.startsWith('k')); // -1
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int indexWhere(bool test(E element), [int start = 0]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/indexWhere.html>
:::
