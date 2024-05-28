[dart:collection](../../dart-collection/dart-collection-library){._links-link}

removeAt method
===============

::: {.section .multi-line-signature}
E removeAt(

1.  [int](../../dart-core/int-class) index

)

::: {.features}
override
:::
:::

Removes the object at position `index` from this list.

This method reduces the length of `this` by one and moves all later
objects down by one position.

Returns the removed value.

The `index` must be in the range `0 ≤ index < length`. The list must be
growable.

``` {.language-dart data-language="dart"}
final parts = <String>['head', 'shoulder', 'knees', 'toes'];
final retVal = parts.removeAt(2); // knees
print(parts); // [head, shoulder, toes]
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
E removeAt(int index) {
  E result = this[index];
  _closeGap(index, index + 1);
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListMixin/removeAt.html>
:::
