[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

values constant
===============

::: {.section .multi-line-signature}
[List](../../dart-core/list-class)\<[Abi](../abi-class)\> const values
:::

The ABIs that the DartVM can run on.

Does not contain a `macosIA32`. We have stopped supporting 32-bit MacOS.

Includes [windowsArm64](windowsarm64-constant), even though it is
currently not supported. Support has been requested for Flutter.
<https://github.com/flutter/flutter/issues/53120>

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
// TODO(http://dartbug.com/47824): Remove the above comment when supported.
static const values = [
  androidArm,
  androidArm64,
  androidIA32,
  androidX64,
  fuchsiaArm64,
  fuchsiaX64,
  iosArm,
  iosArm64,
  iosX64,
  linuxArm,
  linuxArm64,
  linuxIA32,
  linuxX64,
  linuxRiscv32,
  linuxRiscv64,
  macosArm64,
  macosX64,
  windowsArm64,
  windowsIA32,
  windowsX64,
];
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Abi/values-constant.html>
:::
