[dart:core](../../dart-core/dart-core-library){._links-link}

int.fromEnvironment constructor
===============================

::: {.section .multi-line-signature}
const int.fromEnvironment(

1.  [String](../string-class) name,
2.  {[int](../int-class) defaultValue = 0}

)
:::

Returns the integer value of the given environment declaration `name`.

The result is the same as would be returned by:

``` {.language-dart data-language="dart"}
int.tryParse(const String.fromEnvironment(name, defaultValue: ""))
    ?? defaultValue
```

Example:

``` {.language-dart data-language="dart"}
const int.fromEnvironment("defaultPort", defaultValue: 80)
```

The string value, or lack of a value, associated with a `name` must be
consistent across all calls to
[String.fromEnvironment](../string/string.fromenvironment),
`int.fromEnvironment`,
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
external const factory int.fromEnvironment(String name,
    {int defaultValue = 0});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/int/int.fromEnvironment.html>
:::
