[dart:collection](../../dart-collection/dart-collection-library){._links-link}

remove method
=============

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) remove(

1.  [Object](../../dart-core/object-class)? object

)

::: {.features}
override
:::
:::

Removes `value` from the set.

Returns `true` if `value` was in the set, and `false` if not. The method
has no effect if `value` was not in the set.

``` {.language-dart data-language="dart"}
final characters = <String>{'A', 'B', 'C'};
final didRemoveB = characters.remove('B'); // true
final didRemoveD = characters.remove('D'); // false
print(characters); // {A, C}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool remove(Object? object) {
  if (!_validKey(object)) return false;
  return _remove(object as E) != null;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeSet/remove.html>
:::
