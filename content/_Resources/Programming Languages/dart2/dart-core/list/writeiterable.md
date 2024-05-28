[dart:core](../../dart-core/dart-core-library){._links-link}

writeIterable\<T\> method
=========================

::: {.section .multi-line-signature}
void writeIterable\<T\>(

1.  [List](../list-class)\<T\> target,
2.  [int](../int-class) at,
3.  [Iterable](../iterable-class)\<T\> source

)
:::

Write the elements of an iterable into a list.

This is a utility function that can be used to implement methods like
[setAll](setall).

The elements of `source` are written into `target` from position `at`.
The `source` must not contain more elements after writing the last
position of `target`.

If the source is a list, the [copyRange](copyrange) function is likely
to be more efficient.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static void writeIterable<T>(List<T> target, int at, Iterable<T> source) {
  RangeError.checkValueInInterval(at, 0, target.length, "at");
  int index = at;
  int targetLength = target.length;
  for (var element in source) {
    if (index == targetLength) {
      throw IndexError(targetLength, target);
    }
    target[index] = element;
    index++;
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/writeIterable.html>
:::
