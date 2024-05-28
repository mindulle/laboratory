[dart:io](../../dart-io/dart-io-library){._links-link}

add method
==========

::: {.section .multi-line-signature}
void add(

1.  [String](../../dart-core/string-class) name,
2.  [Object](../../dart-core/object-class) value,
3.  {\@Since(\"2.8\") [bool](../../dart-core/bool-class)
    preserveHeaderCase = false}

)
:::

Adds a header value.

The header named `name` will have a string value derived from `value`
added to its list of values.

Some headers are single valued, and for these, adding a value will
replace a previous value. If the `value` is a
[DateTime](../../dart-core/datetime-class), an HTTP date format will be
applied. If the value is an [Iterable](../../dart-core/iterable-class),
each element will be added separately. For all other types the default
[Object.toString](../../dart-core/object/tostring) method will be used.

Header names are converted to lower-case unless `preserveHeaderCase` is
set to true. If two header names are the same when converted to
lower-case, they are considered to be the same header, with one set of
values.

The current case of the a header name is that of the name used by the
last [set](set) or [add](add) call for that header.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void add(String name, Object value,
    {@Since("2.8") bool preserveHeaderCase = false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpHeaders/add.html>
:::
