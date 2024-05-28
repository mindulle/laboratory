[dart:io](../../dart-io/dart-io-library){._links-link}

remove method
=============

::: {.section .multi-line-signature}
void remove(

1.  [String](../../dart-core/string-class) name,
2.  [Object](../../dart-core/object-class) value

)
:::

Removes a specific value for a header name.

Some headers have system supplied values which cannot be removed. For
all other headers and values, the `value` is converted to a string in
the same way as for [add](add), then that string value is removed from
the current values of `name`. If there are no remaining values for
`name`, the header is no longer considered present.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void remove(String name, Object value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpHeaders/remove.html>
:::
