[dart:core](../../dart-core/dart-core-library){._links-link}

hashCode property
=================

::: {#getter .section .multi-line-signature}
[int](../int-class) hashCode

::: {.features}
override
:::
:::

Returns a hash code for a numerical value.

The hash code is compatible with equality. It returns the same value for
an [int](../int-class) and a [double](../double-class) with the same
numerical value, and therefore the same value for the doubles zero and
minus zero.

No guarantees are made about the hash code of NaN values.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get hashCode;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/hashCode.html>
:::
