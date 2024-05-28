[dart:io](../../dart-io/dart-io-library){._links-link}

rename method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Link](../link-class)\> rename(

1.  [String](../../dart-core/string-class) newPath

)

::: {.features}
override
:::
:::

Renames this link.

Returns a `Future<Link>` that completes with a `Link` for the renamed
link.

If `newPath` identifies an existing link, that link is removed first. If
`newPath` identifies an existing file or directory, the operation fails
and the future completes with an exception.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Link> rename(String newPath);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Link/rename.html>
:::
