[dart:collection](../../dart-collection/dart-collection-library){._links-link}

map\<T\> method
===============

::: {.section .multi-line-signature}
[Iterable](../../dart-core/iterable-class)\<T\> map\<T\>(

1.  T toElement(
    1.  E element

    )

)

::: {.features}
inherited
:::
:::

The current elements of this iterable modified by `toElement`.

Returns a new lazy [Iterable](../../dart-core/iterable-class) with
elements that are created by calling `toElement` on each element of this
`Iterable` in iteration order.

The returned iterable is lazy, so it won\'t iterate the elements of this
iterable until it is itself iterated, and then it will apply `toElement`
to create one element at a time. The converted elements are not cached.
Iterating multiple times over the returned
[Iterable](../../dart-core/iterable-class) will invoke the supplied
`toElement` function once per element for on each iteration.

Methods on the returned iterable are allowed to omit calling `toElement`
on any element where the result isn\'t needed. For example,
[elementAt](elementat) may call `toElement` only once.

Equivalent to:

``` {.language-dart data-language="dart"}
Iterable<T> map<T>(T toElement(E e)) sync* {
  for (var value in this) {
    yield toElement(value);
  }
}
```

Example:

``` {.language-dart data-language="dart"}
var products = jsonDecode('''
[
  {"name": "Screwdriver", "price": 42.00},
  {"name": "Wingnut", "price": 0.50}
]
''');
var values = products.map((product) => product['price'] as double);
var totalPrice = values.fold(0.0, (a, b) => a + b); // 42.5.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Iterable<T> map<T>(T toElement(E element)) =>
    MappedListIterable<E, T>(this, toElement);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListQueue/map.html>
:::
