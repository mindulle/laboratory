[dart:core](../dart-core/dart-core-library){._links-link}

override top-level constant
===========================

::: {.section .multi-line-signature}
[Object](object-class) const override
:::

Annotation on an instance members which override an interface member.

Annotations have no effect on the meaning of a Dart program. This
annotation is recognized by the Dart analyzer, and it allows the
analyzer to provide hints or warnings for some potential problems of an
otherwise valid program. As such, the meaning of this annotation is
defined by the Dart analyzer.

The `@override` annotation expresses the intent that a declaration
*should* override an interface method, something which is not visible
from the declaration itself. This extra information allows the analyzer
to provide a warning when that intent is not satisfied, where a member
is intended to override a superclass member or implement an interface
member, but fails to do so. Such a situation can arise if a member name
is mistyped, or if the superclass renames the member.

The `@override` annotation applies to instance methods, instance
getters, instance setters and instance variables (fields). When applied
to an instance variable, it means that the variable\'s implicit getter
and setter (if any) are marked as overriding. It has no effect on the
variable itself.

Further [lints](https://dart-lang.github.io/linter/lints/) can be used
to enable more warnings based on `@override` annotations.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const Object override = _Override();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/override-constant.html>
:::
