[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

delegate method
===============

::: {.section .multi-line-signature}
dynamic delegate(

1.  [Invocation](../../dart-core/invocation-class) invocation

)
:::

Performs `invocation` on the reflectee of this
[ObjectMirror](../objectmirror-class).

Equivalent to

``` {.language-dart data-language="dart"}
if (invocation.isGetter) {
  return this.getField(invocation.memberName).reflectee;
} else if (invocation.isSetter) {
  return this.setField(invocation.memberName,
                       invocation.positionalArguments[0]).reflectee;
} else {
  return this.invoke(invocation.memberName,
                     invocation.positionalArguments,
                     invocation.namedArguments).reflectee;
}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
delegate(Invocation invocation);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/ObjectMirror/delegate.html>
:::
