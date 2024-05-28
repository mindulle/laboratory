[dart:core](../../dart-core/dart-core-library){._links-link}

Invocation.setter constructor
=============================

::: {.section .multi-line-signature}
Invocation.setter(

1.  [Symbol](../symbol-class) memberName,
2.  [Object](../object-class)? argument

)
:::

Creates an invocation corresponding to a setter invocation.

This constructor accepts any [Symbol](../symbol-class) as `memberName`,
but remember that *actual setter names* end in `=`, so the invocation
corresponding to `object.member = value` is

``` {.language-dart data-language="dart"}
Invocation.setter(const Symbol("member="), value)
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Invocation.setter(Symbol memberName, Object? argument) =
    _Invocation.setter;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Invocation/Invocation.setter.html>
:::
