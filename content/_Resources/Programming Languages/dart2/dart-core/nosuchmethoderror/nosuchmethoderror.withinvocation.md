[dart:core](../../dart-core/dart-core-library){._links-link}

NoSuchMethodError.withInvocation constructor
============================================

::: {.section .multi-line-signature}
NoSuchMethodError.withInvocation(

1.  [Object](../object-class)? receiver,
2.  [Invocation](../invocation-class) invocation

)
:::

Creates a [NoSuchMethodError](../nosuchmethoderror-class) corresponding
to a failed method call.

The `receiver` is the receiver of the method call. That is, the object
on which the method was attempted called.

The `invocation` represents the method call that failed. It should not
be `null`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory NoSuchMethodError.withInvocation(
    Object? receiver, Invocation invocation);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/NoSuchMethodError/NoSuchMethodError.withInvocation.html>
:::
