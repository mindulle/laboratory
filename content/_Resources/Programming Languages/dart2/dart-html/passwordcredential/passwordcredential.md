[dart:html](../../dart-html/dart-html-library){._links-link}

PasswordCredential constructor
==============================

::: {.section .multi-line-signature}
PasswordCredential(

1.  dynamic data\_OR\_form

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory PasswordCredential(data_OR_form) {
  if ((data_OR_form is Map)) {
    var data_1 = convertDartToNative_Dictionary(data_OR_form);
    return PasswordCredential._create_1(data_1);
  }
  if ((data_OR_form is FormElement)) {
    return PasswordCredential._create_2(data_OR_form);
  }
  throw new ArgumentError("Incorrect number or type of arguments");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/PasswordCredential/PasswordCredential.html>
:::
