[dart:developer](../dart-developer/dart-developer-library){._links-link}

ServiceExtensionResponse class
==============================

A response to a service protocol extension RPC.

If the RPC was successful, use
[ServiceExtensionResponse.result](serviceextensionresponse/result),
otherwise use
[ServiceExtensionResponse.error](serviceextensionresponse/serviceextensionresponse.error).

Constructors
------------

[ServiceExtensionResponse.error](serviceextensionresponse/serviceextensionresponse.error)([int](../dart-core/int-class) errorCode, [String](../dart-core/string-class) errorDetail)
:   Creates an error response to a service protocol extension RPC.

[ServiceExtensionResponse.result](serviceextensionresponse/serviceextensionresponse.result)([String](../dart-core/string-class) result)
:   Creates a successful response to a service protocol extension RPC.

Properties {#instance-properties}
----------

[errorCode](serviceextensionresponse/errorcode) →
[int](../dart-core/int-class)?

::: {.features}
final
:::

The error code associated with a failed service protocol extension RPC.

[errorDetail](serviceextensionresponse/errordetail) →
[String](../dart-core/string-class)?

::: {.features}
final
:::

The details of a failed service protocol extension RPC.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[result](serviceextensionresponse/result) →
[String](../dart-core/string-class)?

::: {.features}
final
:::

The result of a successful service protocol extension RPC.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[isError](serviceextensionresponse/iserror)() →
[bool](../dart-core/bool-class)

Determines if this response represents an error.

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

Constants
---------

[extensionError](serviceextensionresponse/extensionerror-constant) → const [int](../dart-core/int-class)
:   Generic extension error code.
    <div>

    `-32000`

    </div>

[extensionErrorMax](serviceextensionresponse/extensionerrormax-constant) → const [int](../dart-core/int-class)
:   Maximum extension provided error code.
    <div>

    `-32000`

    </div>

[extensionErrorMin](serviceextensionresponse/extensionerrormin-constant) → const [int](../dart-core/int-class)
:   Minimum extension provided error code.
    <div>

    `-32016`

    </div>

[invalidParams](serviceextensionresponse/invalidparams-constant) → const [int](../dart-core/int-class)
:   Invalid method parameter(s) error code.
    <div>

    `-32602`

    </div>

[kExtensionError](serviceextensionresponse/kextensionerror-constant){.deprecated} → const [int](../dart-core/int-class)
:   Generic extension error code.
    <div>

    `extensionError`

    </div>

[kExtensionErrorMax](serviceextensionresponse/kextensionerrormax-constant){.deprecated} → const [int](../dart-core/int-class)
:   Maximum extension provided error code.
    <div>

    `extensionErrorMax`

    </div>

[kExtensionErrorMin](serviceextensionresponse/kextensionerrormin-constant){.deprecated} → const [int](../dart-core/int-class)
:   Minimum extension provided error code.
    <div>

    `extensionErrorMin`

    </div>

[kInvalidParams](serviceextensionresponse/kinvalidparams-constant){.deprecated} → const [int](../dart-core/int-class)
:   Invalid method parameter(s) error code.
    <div>

    `invalidParams`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/ServiceExtensionResponse-class.html>
:::
