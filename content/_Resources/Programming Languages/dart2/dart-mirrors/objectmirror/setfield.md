[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

setField method
===============

::: {.section .multi-line-signature}
[InstanceMirror](../instancemirror-class) setField(

1.  [Symbol](../../dart-core/symbol-class) fieldName,
2.  dynamic value

)
:::

Invokes a setter and returns a mirror on the result.

The setter may be either the implicit setter for a non-final field or a
user-defined setter method.

Let *o* be the object reflected by this mirror, let *f* be the simple
name of the getter denoted by `fieldName`, and let *a* be the object
bound to `value`.

Then this method will perform the setter invocation *o.f = a* in a scope
that has access to the private members of *o* (if *o* is a class or
library) or the private members of the class of *o* (otherwise).

If the invocation returns a result *r*, this method returns the result
of calling [reflect](../reflect)(`value`).

If the invocation causes a compilation error, the effect is the same as
if a non-reflective compilation error had been encountered.

If the invocation throws an exception *e* (that it does not catch) this
method throws *e*.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
InstanceMirror setField(Symbol fieldName, dynamic value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/ObjectMirror/setField.html>
:::
