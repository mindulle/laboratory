[dart:mirrors](../dart-mirrors/dart-mirrors-library){._links-link}

reflect function
================

::: {.section .multi-line-signature}
[InstanceMirror](instancemirror-class) reflect(

1.  dynamic reflectee

)
:::

Reflects an instance.

Returns an [InstanceMirror](instancemirror-class) reflecting
`reflectee`. If `reflectee` is a function or an instance of a class that
has a `call` method, the returned instance mirror will be a
[ClosureMirror](closuremirror-class).

Note that since one cannot obtain an object from another isolate, this
function can only be used to obtain mirrors on objects of the current
isolate.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external InstanceMirror reflect(dynamic reflectee);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/reflect.html>
:::
