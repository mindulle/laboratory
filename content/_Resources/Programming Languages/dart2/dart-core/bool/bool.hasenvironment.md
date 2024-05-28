[dart:core](../../dart-core/dart-core-library){._links-link}

bool.hasEnvironment constructor
===============================

::: {.section .multi-line-signature}
const bool.hasEnvironment(

1.  [String](../string-class) name

)
:::

Whether there is an environment declaration `name`.

Returns true iff there is an environment declaration with the name
`name` If there is then the value of that declaration can be accessed
using `const String.fromEnvironment(name)`. Otherwise,
`String.fromEnvironment(name, defaultValue: someString)` will evaluate
to the given `defaultValue`.

This constructor can be used to handle an absent declaration
specifically, in ways that cannot be represented by providing a default
value to the `C.fromEnvironment` constructor where `C` is one of
[String](../string-class), [int](../int-class), or
[bool](../bool-class).

Example:

``` {.language-dart data-language="dart"}
const loggingIsDeclared = bool.hasEnvironment("logging");

const String? logger = loggingIsDeclared
    ? String.fromEnvironment("logging")
    : null;
```

The string value, or lack of a value, associated with a `name` must be
consistent across all calls to
[String.fromEnvironment](../string/string.fromenvironment),
[int.fromEnvironment](../int/int.fromenvironment),
[bool.fromEnvironment](bool.fromenvironment) and `bool.hasEnvironment`
in a single program.

This constructor is only guaranteed to work when invoked as `const`. It
may work as a non-constant invocation on some platforms which have
access to compiler options at run-time, but most ahead-of-time compiled
platforms will not have this information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
// The .hasEnvironment() constructor is special in that we do not want
// users to call them using "new". We prohibit that by giving them bodies
// that throw, even though const constructors are not allowed to have bodies.
// Disable those static errors.
//ignore: const_constructor_with_body
//ignore: const_factory
external const factory bool.hasEnvironment(String name);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/bool/bool.hasEnvironment.html>
:::
