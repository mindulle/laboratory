[dart:core](../dart-core/dart-core-library){._links-link}

identical function
==================

::: {.section .multi-line-signature}
[bool](bool-class) identical(

1.  [Object](object-class)? a,
2.  [Object](object-class)? b

)
:::

Check whether two references are to the same object.

Example:

``` {.language-dart data-language="dart"}
var o = new Object();
var isIdentical = identical(o, new Object()); // false, different objects.
isIdentical = identical(o, o); // true, same object
isIdentical = identical(const Object(), const Object()); // true, const canonicalizes
isIdentical = identical([1], [1]); // false
isIdentical = identical(const [1], const [1]); // true
isIdentical = identical(const [1], const [2]); // false
isIdentical = identical(2, 1 + 1); // true, integers canonicalizes
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external bool identical(Object? a, Object? b);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/identical.html>
:::
