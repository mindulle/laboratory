[dart:collection](../../dart-collection/dart-collection-library){._links-link}

fold\<T\> method
================

::: {.section .multi-line-signature}
T fold\<T\>(

1.  T initialValue,
2.  T combine(
    1.  T previousValue,
    2.  E element

    )

)

::: {.features}
override
:::
:::

Reduces a collection to a single value by iteratively combining each
element of the collection with an existing value

Uses `initialValue` as the initial value, then iterates through the
elements and updates the value with each element using the `combine`
function, as if by:

``` {.language-dart data-language="dart"}
var value = initialValue;
for (E element in this) {
  value = combine(value, element);
}
return value;
```

Example of calculating the sum of an iterable:

``` {.language-dart data-language="dart"}
final numbers = <double>[10, 2, 5, 0.5];
const initialValue = 100.0;
final result = numbers.fold<double>(
    initialValue, (previousValue, element) => previousValue + element);
print(result); // 117.5
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
T fold<T>(T initialValue, T combine(T previousValue, E element)) {
  var value = initialValue;
  int length = this.length;
  for (int i = 0; i < length; i++) {
    value = combine(value, this[i]);
    if (length != this.length) {
      throw ConcurrentModificationError(this);
    }
  }
  return value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListMixin/fold.html>
:::
