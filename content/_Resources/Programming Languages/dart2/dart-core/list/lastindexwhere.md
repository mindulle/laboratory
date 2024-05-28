[dart:core](../../dart-core/dart-core-library){._links-link}

lastIndexWhere method
=====================

::: {.section .multi-line-signature}
[int](../int-class) lastIndexWhere(

1.  [bool](../bool-class) test(
    1.  E element

    ),
2.  \[[int](../int-class)? start\]

)
:::

The last index in the list that satisfies the provided `test`.

Searches the list from index `start` to 0. The first time an object `o`
is encountered so that `test(o)` is true, the index of `o` is returned.
If `start` is omitted, it defaults to the [length](length) of the list.

``` {.language-dart data-language="dart"}
final notes = <String>['do', 're', 'mi', 're'];
final first = notes.lastIndexWhere((note) => note.startsWith('r')); // 3
final second = notes.lastIndexWhere((note) => note.startsWith('r'),
    2); // 1
```

Returns -1 if `element` is not found.

``` {.language-dart data-language="dart"}
final notes = <String>['do', 're', 'mi', 're'];
final index = notes.lastIndexWhere((note) => note.startsWith('k'));
print(index); // -1
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int lastIndexWhere(bool test(E element), [int? start]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/lastIndexWhere.html>
:::
