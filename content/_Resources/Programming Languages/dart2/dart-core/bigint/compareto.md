[dart:core](../../dart-core/dart-core-library){._links-link}

compareTo method
================

::: {.section .multi-line-signature}
[int](../int-class) compareTo(

1.  [BigInt](../bigint-class) other

)

::: {.features}
override
:::
:::

Compares this to `other`.

Returns a negative number if `this` is less than `other`, zero if they
are equal, and a positive number if `this` is greater than `other`.

Example:

``` {.language-dart data-language="dart"}
print(BigInt.from(1).compareTo(BigInt.from(2))); // => -1
print(BigInt.from(2).compareTo(BigInt.from(1))); // => 1
print(BigInt.from(1).compareTo(BigInt.from(1))); // => 0
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int compareTo(BigInt other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/BigInt/compareTo.html>
:::
