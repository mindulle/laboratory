[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

staticMembers property
======================

::: {#getter .section .multi-line-signature}
[Map](../../dart-core/map-class)\<[Symbol](../../dart-core/symbol-class),
[MethodMirror](../methodmirror-class)\> staticMembers
:::

Returns a map of the static methods, getters and setters of the class.

The intent is to capture those members that constitute the API of a
class. Hence fields are not included, but the getters and setters
implicitly introduced by fields are included.

The map is keyed by the simple names of the members.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Map<Symbol, MethodMirror> get staticMembers;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/ClassMirror/staticMembers.html>
:::
