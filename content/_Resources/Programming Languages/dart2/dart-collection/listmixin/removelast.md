[dart:collection](../../dart-collection/dart-collection-library){._links-link}

removeLast method
=================

::: {.section .multi-line-signature}
E removeLast()

::: {.features}
override
:::
:::

Removes and returns the last object in this list.

The list must be growable and non-empty.

``` {.language-dart data-language="dart"}
final parts = <String>['head', 'shoulder', 'knees', 'toes'];
final retVal = parts.removeLast(); // toes
print(parts); // [head, shoulder, knees]
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
E removeLast() {
  if (length == 0) {
    throw IterableElementError.noElement();
  }
  E result = this[length - 1];
  length--;
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListMixin/removeLast.html>
:::
