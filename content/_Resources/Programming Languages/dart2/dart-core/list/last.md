[dart:core](../../dart-core/dart-core-library){._links-link}

last property
=============

::: {#getter .section .multi-line-signature}
E last

::: {.features}
inherited
:::
:::

Returns the last element.

Throws a [StateError](../stateerror-class) if `this` is empty. Otherwise
may iterate through the elements and returns the last one seen. Some
iterables may have more efficient ways to find the last element (for
example a list can directly access the last element, without iterating
through the previous ones).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
E get last {
  Iterator<E> it = iterator;
  if (!it.moveNext()) {
    throw IterableElementError.noElement();
  }
  E result;
  do {
    result = it.current;
  } while (it.moveNext());
  return result;
}
```

::: {#setter .section .multi-line-signature}
void last=(E value)
:::

The last element of the list.

The list must be non-empty when accessing its last element.

The last element of a list can be modified, unlike an
[Iterable](../iterable-class). A `list.last` is equivalent to
`theList[theList.length - 1]`, both for getting and setting the value.

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3];
print(numbers.last); // 3
numbers.last = 10;
print(numbers.last); // 10
numbers.clear();
numbers.last; // Throws.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void set last(E value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/last.html>
:::
