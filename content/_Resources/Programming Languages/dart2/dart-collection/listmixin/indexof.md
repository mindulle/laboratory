[dart:collection](../../dart-collection/dart-collection-library){._links-link}

indexOf method
==============

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) indexOf(

1.  [Object](../../dart-core/object-class)? element,
2.  \[[int](../../dart-core/int-class) start = 0\]

)

::: {.features}
override
:::
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
int indexOf(Object? element, [int start = 0]) {
  if (start < 0) start = 0;
  for (int i = start; i < this.length; i++) {
    if (this[i] == element) return i;
  }
  return -1;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListMixin/indexOf.html>
:::
