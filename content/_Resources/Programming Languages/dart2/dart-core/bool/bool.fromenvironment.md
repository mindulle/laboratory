[dart:core](../../dart-core/dart-core-library){._links-link}

bool.fromEnvironment constructor
================================

::: {.section .multi-line-signature}
const bool.fromEnvironment(

1.  [String](../string-class) name,
2.  {[bool](../bool-class) defaultValue = false}

)
:::

Returns the boolean value of the environment declaration `name`.

The boolean value of the declaration is `true` if the declared value is
the string `"true"`, and `false` if the value is `"false"`.

In all other cases, including when there is no declaration for `name`,
the result is the `defaultValue`.

The result is the same as would be returned by:

``` {.language-dart data-language="dart"}
(const String.fromEnvironment(name) == "true")
    ? true
    : (const String.fromEnvironment(name) == "false")
        ? false
        : defaultValue
```

Example:

``` {.language-dart data-language="dart"}
const loggingFlag = const bool.fromEnvironment("logging");
```

If you want to use a different truth-string than `"true"`, you can use
the [String.fromEnvironment](../string/string.fromenvironment)
constructor directly:

``` {.language-dart data-language="dart"}
const isLoggingOn = (const String.fromEnvironment("logging") == "on");
```

The string value, or lack of a value, associated with a `name` must be
consistent across all calls to
[String.fromEnvironment](../string/string.fromenvironment),
[int.fromEnvironment](../int/int.fromenvironment),
`bool.fromEnvironment` and [bool.hasEnvironment](bool.hasenvironment) in
a single program.

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
external const factory bool.fromEnvironment(String name,
    {bool defaultValue = false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/bool/bool.fromEnvironment.html>
:::
