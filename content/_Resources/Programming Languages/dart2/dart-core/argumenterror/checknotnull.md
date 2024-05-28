[dart:core](../../dart-core/dart-core-library){._links-link}

checkNotNull\<\@Since(\"2.8\") T\> method
=========================================

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.1\")

</div>

T checkNotNull\<\@Since(\"2.8\") T\>(

1.  T? argument,
2.  \[[String](../string-class)? name\]

)

::: {.features}
\@Since(\"2.1\")
:::
:::

Throws if `argument` is `null`.

If `name` is supplied, it is used as the parameter name in the error
message.

Returns the `argument` if it is not null.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.1")
static T checkNotNull<@Since("2.8") T>(T? argument, [String? name]) {
  if (argument == null) throw ArgumentError.notNull(name);
  return argument;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/ArgumentError/checkNotNull.html>
:::
