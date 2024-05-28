[dart:core](../../dart-core/dart-core-library){._links-link}

NoSuchMethodError constructor
=============================

::: {.section .multi-line-signature}
<div>

1.  @[Deprecated](../deprecated-class)(\"Use NoSuchMethod.withInvocation
    instead\")

</div>

NoSuchMethodError(

1.  [Object](../object-class)? receiver,
2.  [Symbol](../symbol-class) memberName,
3.  [List](../list-class)? positionalArguments,
4.  [Map](../map-class)\<[Symbol](../symbol-class), dynamic\>?
    namedArguments

)
:::

Create a [NoSuchMethodError](../nosuchmethoderror-class) corresponding
to a failed method call.

The `receiver` is the receiver of the method call. That is, the object
on which the method was attempted called. If the receiver is `null`, it
is interpreted as a call to a top-level function of a library.

The `memberName` is a [Symbol](../symbol-class) representing the name of
the called method or accessor.

The `positionalArguments` is a list of the positional arguments that the
method was called with. If `null`, it is considered equivalent to the
empty list.

The `namedArguments` is a map from [Symbol](../symbol-class)s to the
values of named arguments that the method was called with. If `null`, it
is considered equivalent to the empty map.

This constructor does not handle type arguments. To include type
variables, create an [Invocation](../invocation-class) and use
[NoSuchMethodError.withInvocation](nosuchmethoderror.withinvocation).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Deprecated("Use NoSuchMethod.withInvocation instead")
external NoSuchMethodError(Object? receiver, Symbol memberName,
    List? positionalArguments, Map<Symbol, dynamic>? namedArguments);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/NoSuchMethodError/NoSuchMethodError.html>
:::
