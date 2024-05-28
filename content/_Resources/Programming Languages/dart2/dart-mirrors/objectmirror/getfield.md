[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

getField method
===============

::: {.section .multi-line-signature}
[InstanceMirror](../instancemirror-class) getField(

1.  [Symbol](../../dart-core/symbol-class) fieldName

)
:::

Invokes a getter and returns a mirror on the result.

The getter can be the implicit getter for a field or a user-defined
getter method.

Let *o* be the object reflected by this mirror, let *f* be the simple
name of the getter denoted by `fieldName`.

Then this method will perform the getter invocation *o.f* in a scope
that has access to the private members of *o* (if *o* is a class or
library) or the private members of the class of *o* (otherwise).

If this mirror is an [InstanceMirror](../instancemirror-class), and
`fieldName` denotes an instance method on its reflectee, the result of
the invocation is an instance mirror on a closure corresponding to that
method.

If this mirror is a [LibraryMirror](../librarymirror-class), and
`fieldName` denotes a top-level method in the corresponding library, the
result of the invocation is an instance mirror on a closure
corresponding to that method.

If this mirror is a [ClassMirror](../classmirror-class), and `fieldName`
denotes a static method in the corresponding class, the result of the
invocation is an instance mirror on a closure corresponding to that
method.

If the invocation returns a result *r*, this method returns the result
of calling [reflect](../reflect)(*r*).

If the invocation causes a compilation error, the effect is the same as
if a non-reflective compilation error had been encountered.

If the invocation throws an exception *e* (that it does not catch), this
method throws *e*.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
// TODO(ahe): Remove stuff about scope and private members. [fieldName] is a
// capability giving access to private members.
InstanceMirror getField(Symbol fieldName);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/ObjectMirror/getField.html>
:::
