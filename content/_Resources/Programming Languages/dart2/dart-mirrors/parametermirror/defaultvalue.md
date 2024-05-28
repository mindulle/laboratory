[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

defaultValue property
=====================

::: {#getter .section .multi-line-signature}
[InstanceMirror](../instancemirror-class)? defaultValue
:::

Returns the default value of an optional parameter.

Returns an [InstanceMirror](../instancemirror-class) on the
(compile-time constant) default value for an optional parameter. If no
default value is declared, it defaults to `null` and a mirror of `null`
is returned.

Returns `null` for a required parameter.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
InstanceMirror? get defaultValue;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/ParameterMirror/defaultValue.html>
:::
