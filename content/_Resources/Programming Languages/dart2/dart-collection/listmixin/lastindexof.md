[dart:collection](../../dart-collection/dart-collection-library){._links-link}

lastIndexOf method
==================

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) lastIndexOf(

1.  [Object](../../dart-core/object-class)? element,
2.  \[[int](../../dart-core/int-class)? start\]

)

::: {.features}
override
:::
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
int lastIndexOf(Object? element, [int? start]) {
  if (start == null || start >= this.length) start = this.length - 1;

  // TODO(38493): The previous line should promote.
  if (start == null) throw "!";

  for (int i = start; i >= 0; i--) {
    if (this[i] == element) return i;
  }
  return -1;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListMixin/lastIndexOf.html>
:::
