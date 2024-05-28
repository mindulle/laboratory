[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

trimmedText property
====================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) trimmedText

::: {.features}
final
:::
:::

The comment text without the start, end, and padding text.

For example, if [text](text) is `/** Comment text. */` then the
[trimmedText](trimmedtext) is `Comment text.`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
* is [: Comment text. :].
 */
final String trimmedText;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/Comment/trimmedText.html>
:::
