[dart:svg](../../dart-svg/dart-svg-library){._links-link}

reduce method
=============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) reduce(

1.  [String](../../dart-core/string-class) combine(
    1.  [String](../../dart-core/string-class) value,
    2.  [String](../../dart-core/string-class) element

    )

)

::: {.features}
inherited
:::
:::

Reduces a collection to a single value by iteratively combining elements
of the collection using the provided function.

The iterable must have at least one element. If it has only one element,
that element is returned.

Otherwise this method starts with the first element from the iterator,
and then combines it with the remaining elements in iteration order, as
if by:

``` {.language-dart data-language="dart"}
E value = iterable.first;
iterable.skip(1).forEach((element) {
  value = combine(value, element);
});
return value;
```

Example of calculating the sum of an iterable:

``` {.language-dart data-language="dart"}
final numbers = <double>[10, 2, 5, 0.5];
final result = numbers.reduce((value, element) => value + element);
print(result); // 17.5
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String reduce(String combine(String value, String element)) {
  return readClasses().reduce(combine);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/AttributeClassSet/reduce.html>
:::
