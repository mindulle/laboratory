[dart:core](../../dart-core/dart-core-library){._links-link}

compareTo method
================

::: {.section .multi-line-signature}
[int](../int-class) compareTo(

1.  [DateTime](../datetime-class) other

)

::: {.features}
override
:::
:::

Compares this DateTime object to `other`, returning zero if the values
are equal.

A [compareTo](compareto) function returns:

-   a negative value if this DateTime [isBefore](isbefore) `other`.
-   `0` if this DateTime [isAtSameMomentAs](isatsamemomentas) `other`,
    and
-   a positive value otherwise (when this DateTime [isAfter](isafter)
    `other`).

``` {.language-dart data-language="dart"}
final now = DateTime.now();
final future = now.add(const Duration(days: 2));
final past = now.subtract(const Duration(days: 2));
final newDate = now.toUtc();

print(now.compareTo(future)); // -1
print(now.compareTo(past)); // 1
print(now.compareTo(newDate)); // 0
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external int compareTo(DateTime other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/compareTo.html>
:::
