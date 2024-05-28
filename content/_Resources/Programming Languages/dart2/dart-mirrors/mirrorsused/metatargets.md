[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

metaTargets property
====================

::: {.section .multi-line-signature}
dynamic metaTargets

::: {.features}
final
:::
:::

A list of classes that when used as metadata indicates a reflective
target. See also [targets](targets).

The following text is non-normative:

The format for specifying the list of classes is the same as used for
specifying [targets](targets). However, as a library cannot be used as a
metadata annotation in Dart, adding a library to the list of
[metaTargets](metatargets) has no effect. In particular, adding a
library to [metaTargets](metatargets) does not make the library\'s
classes valid metadata annotations to enable reflection.

If an instance of a class specified in [metaTargets](metatargets) is
used as metadata annotation on a library, class, field or method, that
library, class, field or method is added to the set of targets for
reflection.

Example usage:

``` {.language-dart data-language="dart"}
library example;
@MirrorsUsed(metaTargets: "example.Reflectable")
import "dart:mirrors";

class Reflectable {
  const Reflectable();
}

class Foo {
  @Reflectable()
  reflectableMethod() { ... }

  nonReflectableMethod() { ... }
}
```

In the above example. `reflectableMethod` is marked as reflectable by
using the `Reflectable` class, which in turn is specified in the
[metaTargets](metatargets) annotation.

The method `nonReflectableMethod` lacks a metadata annotation and thus
will not be reflectable at runtime.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final metaTargets;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/MirrorsUsed/metaTargets.html>
:::
