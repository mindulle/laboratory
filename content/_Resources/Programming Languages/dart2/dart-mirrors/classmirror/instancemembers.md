[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

instanceMembers property
========================

::: {#getter .section .multi-line-signature}
[Map](../../dart-core/map-class)\<[Symbol](../../dart-core/symbol-class),
[MethodMirror](../methodmirror-class)\> instanceMembers
:::

Returns a map of the methods, getters and setters of an instance of the
class.

The intent is to capture those members that constitute the API of an
instance. Hence fields are not included, but the getters and setters
implicitly introduced by fields are included. The map includes methods,
getters and setters that are inherited as well as those introduced by
the class itself.

The map is keyed by the simple names of the members.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Map<Symbol, MethodMirror> get instanceMembers;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/ClassMirror/instanceMembers.html>
:::
