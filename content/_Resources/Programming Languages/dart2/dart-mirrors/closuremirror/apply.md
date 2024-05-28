[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

apply method
============

::: {.section .multi-line-signature}
[InstanceMirror](../instancemirror-class) apply(

1.  [List](../../dart-core/list-class) positionalArguments,
2.  \[[Map](../../dart-core/map-class)\<[Symbol](../../dart-core/symbol-class),
    dynamic\> namedArguments = const \<Symbol, dynamic\>{}\]

)
:::

Executes the closure and returns a mirror on the result.

Let *f* be the closure reflected by this mirror, let *a1, \..., an* be
the elements of `positionalArguments`, let *k1, \..., km* be the
identifiers denoted by the elements of `namedArguments`.keys, and let
*v1, \..., vm* be the elements of `namedArguments`.values.

Then this method will perform the method invocation *f(a1, \..., an, k1:
v1, \..., km: vm)*.

If the invocation returns a result *r*, this method returns the result
of calling [reflect](../reflect)(*r*).

If the invocation causes a compilation error, the effect is the same as
if a non-reflective compilation error had been encountered.

If the invocation throws an exception *e* (that it does not catch), this
method throws *e*.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
InstanceMirror apply(List<dynamic> positionalArguments,
    [Map<Symbol, dynamic> namedArguments = const <Symbol, dynamic>{}]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/ClosureMirror/apply.html>
:::
