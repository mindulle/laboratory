[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

isDocComment property
=====================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) isDocComment

::: {.features}
final
:::
:::

Is `true` if this comment is a documentation comment.

That is, that the comment is either enclosed in `/** ... */` or starts
with `///`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
* with [: /// :].
 */
final bool isDocComment;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/Comment/isDocComment.html>
:::
