[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

function property
=================

::: {#getter .section .multi-line-signature}
[MethodMirror](../methodmirror-class) function
:::

A mirror on the function associated with this closure.

The function associated with an implicit closure of a function is that
function.

The function associated with an instance of a class that has a `call`
method is that `call` method.

A Dart implementation might choose to create a class for each closure
expression, in which case `function` would be the same as
`type.declarations[#call]`. But the Dart language model does not require
this. A more typical implementation involves a single closure class for
each type signature, where the call method dispatches to a function held
in the closure rather the call method directly implementing the closure
body. So one cannot rely on closures from distinct closure expressions
having distinct classes (`type`), but one can rely on them having
distinct functions (`function`).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
MethodMirror get function;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/ClosureMirror/function.html>
:::
