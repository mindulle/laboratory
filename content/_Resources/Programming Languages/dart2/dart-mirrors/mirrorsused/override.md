[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

override property
=================

::: {.section .multi-line-signature}
dynamic override

::: {.features}
final
:::
:::

A list of library names or \"\*\".

When used as metadata on an import of \"dart:mirrors\", this metadata
does not apply to the library in which the annotation is used, but
instead applies to the other libraries (all libraries if \"\*\" is
used).

The following text is non-normative:

Dart2js currently supports the following formats to specify libraries:

-   A constant [List](../../dart-core/list-class) containing
    [String](../../dart-core/string-class) constants representing names
    of libraries.
-   A single [String](../../dart-core/string-class) constant whose value
    is a comma-separated list of library names.

Conceptually, a [MirrorsUsed](../mirrorsused-class){.deprecated}
annotation with [override](override) has the same effect as placing the
annotation directly on the import of `dart:mirrors` in each of the
referenced libraries. Thus, if the library had no
[MirrorsUsed](../mirrorsused-class){.deprecated} annotation before, its
unconditional import of `dart:mirrors` is overridden by an annotated
import.

Note that, like multiple explicit
[MirrorsUsed](../mirrorsused-class){.deprecated} annotations, using
override on a library with an existing
[MirrorsUsed](../mirrorsused-class){.deprecated} annotation is additive.
That is, the overall set of reflective targets is the union of the
reflective targets that arise from the original and the overriding
[MirrorsUsed](../mirrorsused-class){.deprecated} annotations.

The use of [override](override) is only meaningful for libraries that
have an import of `dart:mirrors` without annotation because otherwise it
would work exactly the same way without the [override](override)
parameter.

While the annotation will apply to the given target libraries, the
[symbols](symbols), [targets](targets) and [metaTargets](metatargets)
are still evaluated in the scope of the annotation. Thus, to select a
target from library `foo`, a qualified name has to be used or, if the
target is visible in the current scope, its type may be referenced.

For example, the following code marks all targets in the library `foo`
as reflectable that have a metadata annotation using the `Reflectable`
class from the same library.

``` {.language-dart data-language="dart"}
@MirrorsUsed(metaTargets: "foo.Reflectable", override: "foo")
```

However, the following code would require the use of the `Reflectable`
class from the current library, instead.

``` {.language-dart data-language="dart"}
@MirrorsUsed(metaTargets: "Reflectable", override: "foo")
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final override;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/MirrorsUsed/override.html>
:::
