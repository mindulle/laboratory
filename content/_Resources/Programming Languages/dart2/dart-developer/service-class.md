[dart:developer](../dart-developer/dart-developer-library){._links-link}

Service class
=============

Access information about the service protocol and control the web server
that provides access to the services provided by the Dart VM for
debugging and inspecting Dart programs.

Constructors
------------

[Service](service/service)()

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

Static Methods
--------------

[controlWebServer](service/controlwebserver)({[bool](../dart-core/bool-class) enable = false, [bool](../dart-core/bool-class)? silenceOutput}) → [Future](../dart-async/future-class)\<[ServiceProtocolInfo](serviceprotocolinfo-class)\>
:   Control the web server that the service protocol is accessed
    through. `enable` is used as a toggle to enable or disable the web
    server servicing requests. If `silenceOutput` is provided and is
    true, the server will not output information to the console.

[getInfo](service/getinfo)() → [Future](../dart-async/future-class)\<[ServiceProtocolInfo](serviceprotocolinfo-class)\>
:   Get information about the service protocol (version number and Uri
    to access the service).

[getIsolateID](service/getisolateid)([Isolate](../dart-isolate/isolate-class) isolate) → [String](../dart-core/string-class)?
:   Returns a [String](../dart-core/string-class) token representing the
    ID of `isolate`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/Service-class.html>
:::
