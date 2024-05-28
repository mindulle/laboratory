[dart:core](../../dart-core/dart-core-library){._links-link}

operator \^ method
==================

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.1\")

</div>

[bool](../bool-class) operator \^(

1.  [bool](../bool-class) other

)

::: {.features}
\@Since(\"2.1\")
:::
:::

The logical exclusive disjunction (\"exclusive or\") of this and
`other`.

Returns whether this and `other` are neither both `true` nor both
`false`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.1")
bool operator ^(bool other) => !other == this;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/bool/operator_bitwise_exclusive_or.html>
:::
