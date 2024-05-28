[dart:html](../../dart-html/dart-html-library){._links-link}

first property
==============

::: {#getter .section .multi-line-signature}
[Rectangle](../../dart-math/rectangle-class)\<[num](../../dart-core/num-class)\>
first

::: {.features}
override
:::
:::

Returns the first element.

Throws a [StateError](../../dart-core/stateerror-class) if `this` is
empty. Otherwise returns the first element in the iteration order,
equivalent to `this.elementAt(0)`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Rectangle get first {
  if (this.length > 0) {
    return JS('Rectangle', '#[0]', this);
  }
  throw new StateError("No elements");
}
```

::: {#setter .section .multi-line-signature}
void
first=([Rectangle](../../dart-math/rectangle-class)\<[num](../../dart-core/num-class)\>
value)

::: {.features}
inherited
:::
:::

The first element of the list.

The list must be non-empty when accessing its first element.

The first element of a list can be modified, unlike an
[Iterable](../../dart-core/iterable-class). A `list.first` is equivalent
to `list[0]`, both for getting and setting the value.

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
void set first(E value) {
  if (length == 0) throw IterableElementError.noElement();
  this[0] = value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DomRectList/first.html>
:::
