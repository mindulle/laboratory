[dart:core](../../dart-core/dart-core-library){._links-link}

compareTo method
================

::: {.section .multi-line-signature}
[int](../int-class) compareTo(

1.  [String](../string-class) other

)

::: {.features}
override
:::
:::

Compares this string to `other`.

Returns a negative value if `this` is ordered before `other`, a positive
value if `this` is ordered after `other`, or zero if `this` and `other`
are equivalent.

The ordering is the same as the ordering of the code units at the first
position where the two strings differ. If one string is a prefix of the
other, then the shorter string is ordered before the longer string. If
the strings have exactly the same content, they are equivalent with
regard to the ordering. Ordering does not check for Unicode equivalence.
The comparison is case sensitive.

``` {.language-dart data-language="dart"}
var relation = 'Dart'.compareTo('Go');
print(relation); // < 0
relation = 'Go'.compareTo('Forward');
print(relation); // > 0
relation = 'Forward'.compareTo('Forward');
print(relation); // 0
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int compareTo(String other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/compareTo.html>
:::
