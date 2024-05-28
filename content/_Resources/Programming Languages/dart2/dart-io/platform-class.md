[dart:io](../dart-io/dart-io-library){._links-link}

Platform class
==============

Information about the environment in which the current program is
running.

Platform provides information such as the operating system, the hostname
of the computer, the value of environment variables, the path to the
running program, and other global properties of the program being run.

Get the URI of the current Dart script
--------------------------------------

Use the [script](platform/script) getter to get the URI to the currently
running Dart script.

``` {.language-dart data-language="dart"}
import 'dart:io' show Platform;

void main() {
  // Get the URI of the script being run.
  var uri = Platform.script;
  // Convert the URI to a path.
  var path = uri.toFilePath();
}
```

Get the value of an environment variable
----------------------------------------

The [environment](platform/environment) getter returns a the names and
values of environment variables in a [Map](../dart-core/map-class) that
contains key-value pairs of strings. The Map is unmodifiable. This
sample shows how to get the value of the `PATH` environment variable.

``` {.language-dart data-language="dart"}
import 'dart:io' show Platform;

void main() {
  Map<String, String> envVars = Platform.environment;
  print(envVars['PATH']);
}
```

Determine the OS
----------------

You can get the name of the operating system as a string with the
[operatingSystem](platform/operatingsystem) getter. You can also use one
of the static boolean getters: [isMacOS](platform/ismacos),
[isLinux](platform/islinux), [isWindows](platform/iswindows), etc.

``` {.language-dart data-language="dart"}
import 'dart:io' show Platform;

void main() {
  // Get the operating system as a string.
  String os = Platform.operatingSystem;
  // Or, use a predicate getter.
  if (Platform.isMacOS) {
    print('is a Mac');
  } else {
    print('is not a Mac');
  }
}
```

Constructors
------------

[Platform](platform/platform)()

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

Static Properties
-----------------

[environment](platform/environment) →
[Map](../dart-core/map-class)\<[String](../dart-core/string-class),
[String](../dart-core/string-class)\>

::: {.features}
read-only
:::

The environment for this process as a map from string key to string
value.

[executable](platform/executable) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

The path of the executable used to run the script in this isolate.
Usually `dart` when running on the Dart VM or the compiled script name
(`script_name.exe`).

[executableArguments](platform/executablearguments) →
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>

::: {.features}
read-only
:::

The flags passed to the executable used to run the script in this
isolate.

[isAndroid](platform/isandroid) → [bool](../dart-core/bool-class)

::: {.features}
final
:::

Whether the operating system is a version of
[Android](https://en.wikipedia.org/wiki/Android_%28operating_system%29).

[isFuchsia](platform/isfuchsia) → [bool](../dart-core/bool-class)

::: {.features}
final
:::

Whether the operating system is a version of
[Fuchsia](https://en.wikipedia.org/wiki/Google_Fuchsia).

[isIOS](platform/isios) → [bool](../dart-core/bool-class)

::: {.features}
final
:::

Whether the operating system is a version of
[iOS](https://en.wikipedia.org/wiki/IOS).

[isLinux](platform/islinux) → [bool](../dart-core/bool-class)

::: {.features}
final
:::

Whether the operating system is a version of
[Linux](https://en.wikipedia.org/wiki/Linux).

[isMacOS](platform/ismacos) → [bool](../dart-core/bool-class)

::: {.features}
final
:::

Whether the operating system is a version of
[macOS](https://en.wikipedia.org/wiki/MacOS).

[isWindows](platform/iswindows) → [bool](../dart-core/bool-class)

::: {.features}
final
:::

Whether the operating system is a version of [Microsoft
Windows](https://en.wikipedia.org/wiki/Microsoft_Windows).

[localeName](platform/localename) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

Get the name of the current locale.

[localHostname](platform/localhostname) →
[String](../dart-core/string-class)

::: {.features}
read-only
:::

The local hostname for the system.

[numberOfProcessors](platform/numberofprocessors) →
[int](../dart-core/int-class)

::: {.features}
read-only
:::

The number of individual execution units of the machine.

[operatingSystem](platform/operatingsystem) →
[String](../dart-core/string-class)

::: {.features}
read-only
:::

A string representing the operating system or platform.

[operatingSystemVersion](platform/operatingsystemversion) →
[String](../dart-core/string-class)

::: {.features}
read-only
:::

A string representing the version of the operating system or platform.

[packageConfig](platform/packageconfig) →
[String](../dart-core/string-class)?

::: {.features}
read-only
:::

The `--packages` flag passed to the executable used to run the script in
this isolate.

[pathSeparator](platform/pathseparator) →
[String](../dart-core/string-class)

::: {.features}
read-only
:::

The path separator used by the operating system to separate components
in file paths.

[resolvedExecutable](platform/resolvedexecutable) →
[String](../dart-core/string-class)

::: {.features}
read-only
:::

The path of the executable used to run the script in this isolate after
it has been resolved by the OS.

[script](platform/script) → [Uri](../dart-core/uri-class)

::: {.features}
read-only
:::

The absolute URI of the script being run in this isolate.

[version](platform/version) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

The version of the current Dart runtime.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Platform-class.html>
:::
