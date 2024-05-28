[dart:core](../../dart-core/dart-core-library){._links-link}

lastIndexOf method
==================

::: {.section .multi-line-signature}
[int](../int-class) lastIndexOf(

1.  E element,
2.  \[[int](../int-class)? start\]

)
:::

The last index of `element` in this list.

Searches the list backwards from index `start` to 0.

The first time an object `o` is encountered so that `o == element`, the
index of `o` is returned.

``` {.language-dart data-language="dart"}
final notes = <String>['do', 're', 'mi', 're'];
const startIndex = 2;
final index = notes.lastIndexOf('re', startIndex); // 1
```

If `start` is not provided, this method searches from the end of the
list.

``` {.language-dart data-language="dart"}
final notes = <String>['do', 're', 'mi', 're'];
final index = notes.lastIndexOf('re'); // 3
```

Returns -1 if `element` is not found.

``` {.language-dart data-language="dart"}
final notes = <String>['do', 're', 'mi', 're'];
final index = notes.lastIndexOf('fa'); // -1
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int lastIndexOf(E element, [int? start]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/lastIndexOf.html>
:::
