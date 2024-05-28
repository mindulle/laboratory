[dart:developer](../dart-developer/dart-developer-library){._links-link}

debugger function
=================

::: {.section .multi-line-signature}
[bool](../dart-core/bool-class) debugger(

1.  {[bool](../dart-core/bool-class) when = true,
2.  [String](../dart-core/string-class)? message}

)
:::

If `when` is true, stop the program as if a breakpoint were hit at the
following statement.

Returns the value of `when`. Some debuggers may display `message`.

NOTE: When invoked, the isolate will not return until a debugger
continues execution. When running in the Dart VM, the behaviour is the
same regardless of whether or not a debugger is connected. When compiled
to JavaScript, this uses the \"debugger\" statement, and behaves exactly
as that does.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external bool debugger({bool when = true, String? message});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/debugger.html>
:::
