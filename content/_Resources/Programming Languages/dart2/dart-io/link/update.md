[dart:io](../../dart-io/dart-io-library){._links-link}

update method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Link](../link-class)\> update(

1.  [String](../../dart-core/string-class) target

)
:::

Updates the link.

Returns a `Future<Link>` that completes with the link when it has been
updated. Calling [update](update) on a non-existing link will complete
its returned future with an exception.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Link> update(String target);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Link/update.html>
:::
