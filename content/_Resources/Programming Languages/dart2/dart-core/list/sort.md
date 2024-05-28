[dart:core](../../dart-core/dart-core-library){._links-link}

sort method
===========

::: {.section .multi-line-signature}
void sort(

1.  \[[int](../int-class) compare(
    1.  E a,
    2.  E b

    )?\]

)
:::

Sorts this list according to the order specified by the `compare`
function.

The `compare` function must act as a [Comparator](../comparator).

``` {.language-dart data-language="dart"}
final numbers = <String>['two', 'three', 'four'];
// Sort from shortest to longest.
numbers.sort((a, b) => a.length.compareTo(b.length));
print(numbers); // [two, four, three]
```

The default [List](../list-class) implementations use
[Comparable.compare](../comparable/compare) if `compare` is omitted.

``` {.language-dart data-language="dart"}
final numbers = <int>[13, 2, -11, 0];
numbers.sort();
print(numbers); // [-11, 0, 2, 13]
```

In that case, the elements of the list must be
[Comparable](../comparable-class) to each other.

A [Comparator](../comparator) may compare objects as equal (return
zero), even if they are distinct objects. The sort function is not
guaranteed to be stable, so distinct objects that compare as equal may
occur in any order in the result:

``` {.language-dart data-language="dart"}
final numbers = <String>['one', 'two', 'three', 'four'];
numbers.sort((a, b) => a.length.compareTo(b.length));
print(numbers); // [one, two, four, three] OR [two, one, four, three]
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void sort([int compare(E a, E b)?]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/sort.html>
:::
