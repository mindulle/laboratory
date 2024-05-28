[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

operator == method
==================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) operator ==(

1.  [Object](../../dart-core/object-class) other

)

::: {.features}
override
:::
:::

Whether `other` is an [IsolateMirror](../isolatemirror-class) on the
same isolate as this mirror.

The equality holds if and only if

1.  `other` is a mirror of the same kind, and
2.  the isolate being reflected by this mirror is the same isolate being
    reflected by `other`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool operator ==(Object other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/IsolateMirror/operator_equals.html>
:::
