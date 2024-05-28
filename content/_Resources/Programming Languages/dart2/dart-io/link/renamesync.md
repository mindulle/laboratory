[dart:io](../../dart-io/dart-io-library){._links-link}

renameSync method
=================

::: {.section .multi-line-signature}
[Link](../link-class) renameSync(

1.  [String](../../dart-core/string-class) newPath

)

::: {.features}
override
:::
:::

Synchronously renames this link.

Returns a [Link](../link-class) instance for the renamed link.

If `newPath` identifies an existing link, that link is removed first. If
`newPath` identifies an existing file or directory the operation fails
and an exception is thrown.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Link renameSync(String newPath);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Link/renameSync.html>
:::
