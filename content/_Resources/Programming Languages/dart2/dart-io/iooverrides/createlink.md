[dart:io](../../dart-io/dart-io-library){._links-link}

createLink method
=================

::: {.section .multi-line-signature}
[Link](../link-class) createLink(

1.  [String](../../dart-core/string-class) path

)
:::

Returns a new [Link](../link-class) object for the given `path`.

When this override is installed, this function overrides the behavior of
`new Link()` and `new Link.fromUri()`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Link createLink(String path) => new _Link(path);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOOverrides/createLink.html>
:::
