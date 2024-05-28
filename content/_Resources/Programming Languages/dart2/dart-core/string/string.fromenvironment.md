[dart:core](../../dart-core/dart-core-library){._links-link}

String.fromEnvironment constructor
==================================

::: {.section .multi-line-signature}
const String.fromEnvironment(

1.  [String](../string-class) name,
2.  {[String](../string-class) defaultValue = \"\"}

)
:::

The string value of the environment declaration `name`.

Environment declarations are provided by the surrounding system
compiling or running the Dart program. Declarations map a string key to
a string value.

If `name` is not declared in the environment, the result is instead
`defaultValue`.

Example of getting a value:

``` {.language-dart data-language="dart"}
const String.fromEnvironment("defaultFloo", defaultValue: "no floo")
```

In order to check whether a declaration is there at all, use
[bool.hasEnvironment](../bool/bool.hasenvironment). Example:

``` {.language-dart data-language="dart"}
const maybeDeclared = bool.hasEnvironment("maybeDeclared")
    ? String.fromEnvironment("maybeDeclared")
    : null;
```

The string value, or lack of a value, associated with a `name` must be
consistent across all calls to `String.fromEnvironment`,
[int.fromEnvironment](../int/int.fromenvironment),
[bool.fromEnvironment](../bool/bool.fromenvironment) and
[bool.hasEnvironment](../bool/bool.hasenvironment) in a single program.

This constructor is only guaranteed to work when invoked as `const`. It
may work as a non-constant invocation on some platforms which have
access to compiler options at run-time, but most ahead-of-time compiled
platforms will not have this information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
// The .fromEnvironment() constructors are special in that we do not want
// users to call them using "new". We prohibit that by giving them bodies
// that throw, even though const constructors are not allowed to have bodies.
// Disable those static errors.
//ignore: const_constructor_with_body
//ignore: const_factory
external const factory String.fromEnvironment(String name,
    {String defaultValue = ""});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/String.fromEnvironment.html>
:::
