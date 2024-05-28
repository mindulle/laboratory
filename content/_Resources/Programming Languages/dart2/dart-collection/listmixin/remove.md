[dart:collection](../../dart-collection/dart-collection-library){._links-link}

remove method
=============

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) remove(

1.  [Object](../../dart-core/object-class)? element

)

::: {.features}
override
:::
:::

Removes the first occurrence of `value` from this list.

Returns true if `value` was in the list, false otherwise. The list must
be growable.

``` {.language-dart data-language="dart"}
final parts = <String>['head', 'shoulders', 'knees', 'toes'];
final retVal = parts.remove('head'); // true
print(parts); // [shoulders, knees, toes]
```

The method has no effect if `value` was not in the list.

``` {.language-dart data-language="dart"}
final parts = <String>['shoulders', 'knees', 'toes'];
// Note: 'head' has already been removed.
final retVal = parts.remove('head'); // false
print(parts); // [shoulders, knees, toes]
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool remove(Object? element) {
  for (int i = 0; i < this.length; i++) {
    if (this[i] == element) {
      this._closeGap(i, i + 1);
      return true;
    }
  }
  return false;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListMixin/remove.html>
:::
