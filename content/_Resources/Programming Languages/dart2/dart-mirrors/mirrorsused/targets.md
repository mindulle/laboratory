[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

targets property
================

::: {.section .multi-line-signature}
dynamic targets

::: {.features}
final
:::
:::

A list of reflective targets.

Combined with [metaTargets](metatargets), this provides the complete
list of reflective targets used by the library to which this metadata
applies.

The following text is non-normative:

For now, there is no formal description of what a reflective target is.
Informally, a target is a library, a class, a method or a field.

Dart2js currently supports the following formats to specify targets:

-   A constant [List](../../dart-core/list-class) containing
    [String](../../dart-core/string-class) constants representing
    (qualified) names of targets and Dart types.
-   A single [String](../../dart-core/string-class) constant whose value
    is a comma-separated list of (qualified) names.
-   A single Dart type.

A (qualified) name is resolved to a target as follows:

1.  If the qualified name matches a library name, the matching library
    is the target.
2.  Else, find the longest prefix of the name such that the prefix ends
    just before a `.` and is a library name.
3.  Use that library as current scope. If no matching prefix was found,
    use the current library, i.e., the library where the
    [MirrorsUsed](../mirrorsused-class){.deprecated} annotation was
    placed.
4.  Split the remaining suffix (the entire name if no library name was
    found in step 3) into a list of
    [String](../../dart-core/string-class) using `.` as a separator.
5.  Select all targets in the current scope whose name matches a
    [String](../../dart-core/string-class) from the list.

For example:

``` {.language-dart data-language="dart"}
library my.library.one;

class A {
  var aField;
}

library main;

@MirrorsUsed(targets: "my.library.one.A.aField")
import "dart:mirrors";
```

The [MirrorsUsed](../mirrorsused-class){.deprecated} annotation
specifies `A` and `aField` from library `my.library.one` as targets.
This will mark the class `A` as a reflective target. The target
specification for `aField` has no effect, as there is no target in
`my.library.one` with that name.

Note that everything within a target also is available for reflection.
So, if a library is specified as target, all classes in that library
become targets for reflection. Likewise, if a class is a target, all its
methods and fields become targets for reflection. As a consequence,
`aField` in the above example is also a reflective target.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final targets;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/MirrorsUsed/targets.html>
:::
