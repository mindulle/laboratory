[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

invoke method
=============

::: {.section .multi-line-signature}
[InstanceMirror](../instancemirror-class) invoke(

1.  [Symbol](../../dart-core/symbol-class) memberName,
2.  [List](../../dart-core/list-class) positionalArguments,
3.  \[[Map](../../dart-core/map-class)\<[Symbol](../../dart-core/symbol-class),
    dynamic\> namedArguments = const \<Symbol, dynamic\>{}\]

)
:::

Invokes the named function and returns a mirror on the result.

Let *o* be the object reflected by this mirror, let *f* be the simple
name of the member denoted by `memberName`, let *a1, \..., an* be the
elements of `positionalArguments`, let *k1, \..., km* be the identifiers
denoted by the elements of `namedArguments`.keys, and let *v1, \..., vm*
be the elements of `namedArguments`.values. Then this method will
perform the method invocation *o.f(a1, \..., an, k1: v1, \..., km: vm)*
in a scope that has access to the private members of *o* (if *o* is a
class or library) or the private members of the class of *o*
(otherwise).

If the invocation returns a result *r*, this method returns the result
of calling [reflect](../reflect)(*r*).

If the invocation causes a compilation error the effect is the same as
if a non-reflective compilation error had been encountered.

If the invocation throws an exception *e* (that it does not catch), this
method throws *e*.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
InstanceMirror invoke(Symbol memberName, List<dynamic> positionalArguments,
    [Map<Symbol, dynamic> namedArguments = const <Symbol, dynamic>{}]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/ObjectMirror/invoke.html>
:::
