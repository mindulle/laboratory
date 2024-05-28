[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

newInstance method
==================

::: {.section .multi-line-signature}
[InstanceMirror](../instancemirror-class) newInstance(

1.  [Symbol](../../dart-core/symbol-class) constructorName,
2.  [List](../../dart-core/list-class) positionalArguments,
3.  \[[Map](../../dart-core/map-class)\<[Symbol](../../dart-core/symbol-class),
    dynamic\> namedArguments = const \<Symbol, dynamic\>{}\]

)
:::

Invokes the named constructor and returns a mirror on the result.

Let *c* be the class reflected by this mirror, let *a1, \..., an* be the
elements of `positionalArguments`, let *k1, \..., km* be the identifiers
denoted by the elements of `namedArguments`.keys, and let *v1, \..., vm*
be the elements of `namedArguments`.values.

If `constructorName` was created from the empty string, then this method
will execute the instance creation expression *new c(a1, \..., an, k1:
v1, \..., km: vm)* in a scope that has access to the private members of
*c*.

Otherwise, let *f* be the simple name of the constructor denoted by
`constructorName`. Then this method will execute the instance creation
expression *new c.f(a1, \..., an, k1: v1, \..., km: vm)* in a scope that
has access to the private members of *c*.

In either case:

-   If the expression evaluates to a result *r*, this method returns the
    result of calling [reflect](../reflect)(*r*).
-   If evaluating the expression causes a compilation error, the effect
    is the same as if a non-reflective compilation error had been
    encountered.
-   If evaluating the expression throws an exception *e* (that it does
    not catch), this method throws *e*.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
InstanceMirror newInstance(
    Symbol constructorName, List<dynamic> positionalArguments,
    [Map<Symbol, dynamic> namedArguments = const <Symbol, dynamic>{}]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/ClassMirror/newInstance.html>
:::
