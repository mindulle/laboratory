[dart:core](../../dart-core/dart-core-library){._links-link}

first property
==============

::: {#getter .section .multi-line-signature}
E first

::: {.features}
inherited
:::
:::

Returns the first element.

Throws a [StateError](../stateerror-class) if `this` is empty. Otherwise
returns the first element in the iteration order, equivalent to
`this.elementAt(0)`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
E get first {
  Iterator<E> it = iterator;
  if (!it.moveNext()) {
    throw IterableElementError.noElement();
  }
  return it.current;
}
```

::: {#setter .section .multi-line-signature}
void first=(E value)
:::

The first element of the list.

The list must be non-empty when accessing its first element.

The first element of a list can be modified, unlike an
[Iterable](../iterable-class). A `list.first` is equivalent to
`list[0]`, both for getting and setting the value.

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3];
print(numbers.first); // 1
numbers.first = 10;
print(numbers.first); // 10
numbers.clear();
numbers.first; // Throws.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void set first(E value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/first.html>
:::
