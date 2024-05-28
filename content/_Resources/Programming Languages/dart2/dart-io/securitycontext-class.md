[dart:io](../dart-io/dart-io-library){._links-link}

SecurityContext class
=====================

The object containing the certificates to trust when making a secure
client connection, and the certificate chain and private key to serve
from a secure server.

The [SecureSocket](securesocket-class) and
[SecureServerSocket](secureserversocket-class) classes take a
SecurityContext as an argument to their connect and bind methods.

Certificates and keys can be added to a SecurityContext from either PEM
or PKCS12 containers.

iOS note: Some methods to add, remove, and inspect certificates are not
yet implemented. However, the platform\'s built-in trusted certificates
can be used, by way of
[SecurityContext.defaultContext](securitycontext/defaultcontext).

Constructors
------------

[SecurityContext](securitycontext/securitycontext)({[bool](../dart-core/bool-class)
withTrustedRoots = false})

::: {.constructor-modifier .features}
factory
:::

Creates a new [SecurityContext](securitycontext-class).

Properties {#instance-properties}
----------

[allowLegacyUnsafeRenegotiation](securitycontext/allowlegacyunsaferenegotiation)
↔ [bool](../dart-core/bool-class)

::: {.features}
read / write
:::

If `true`, the [SecurityContext](securitycontext-class) will allow TLS
renegotiation. Renegotiation is only supported as a client and the
HelloRequest must be received at a quiet point in the application
protocol. This is sufficient to support the legacy use case of
requesting a new client certificate between an HTTP request and response
in (unpipelined) HTTP/1.1. NOTE: Renegotiation is an extremely
problematic protocol feature and should only be used to communicate with
legacy servers in environments where it is known to be safe.

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

[setAlpnProtocols](securitycontext/setalpnprotocols)([List](../dart-core/list-class)\<[String](../dart-core/string-class)\>
protocols, [bool](../dart-core/bool-class) isServer) → void

Sets the list of application-level protocols supported by a client
connection or server connection. The ALPN (application level protocol
negotiation) extension to TLS allows a client to send a list of
protocols in the TLS client hello message, and the server to pick one
and send the selected one back in its server hello message.

[setClientAuthorities](securitycontext/setclientauthorities)([String](../dart-core/string-class)
file, {[String](../dart-core/string-class)? password}) → void

Sets the list of authority names that a
[SecureServerSocket](secureserversocket-class) will advertise as
accepted when requesting a client certificate from a connecting client.

[setClientAuthoritiesBytes](securitycontext/setclientauthoritiesbytes)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
authCertBytes, {[String](../dart-core/string-class)? password}) → void

Sets the list of authority names that a
[SecureServerSocket](secureserversocket-class) will advertise as
accepted, when requesting a client certificate from a connecting client.

[setTrustedCertificates](securitycontext/settrustedcertificates)([String](../dart-core/string-class)
file, {[String](../dart-core/string-class)? password}) → void

Add a certificate to the set of trusted X509 certificates used by
[SecureSocket](securesocket-class) client connections.

[setTrustedCertificatesBytes](securitycontext/settrustedcertificatesbytes)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
certBytes, {[String](../dart-core/string-class)? password}) → void

Add a certificate to the set of trusted X509 certificates used by
[SecureSocket](securesocket-class) client connections.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[useCertificateChain](securitycontext/usecertificatechain)([String](../dart-core/string-class)
file, {[String](../dart-core/string-class)? password}) → void

Sets the chain of X509 certificates served by
[SecureServerSocket](secureserversocket-class) when making secure
connections, including the server certificate.

[useCertificateChainBytes](securitycontext/usecertificatechainbytes)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
chainBytes, {[String](../dart-core/string-class)? password}) → void

Sets the chain of X509 certificates served by
[SecureServerSocket](secureserversocket-class) when making secure
connections, including the server certificate.

[usePrivateKey](securitycontext/useprivatekey)([String](../dart-core/string-class)
file, {[String](../dart-core/string-class)? password}) → void

Sets the private key for a server certificate or client certificate.

[usePrivateKeyBytes](securitycontext/useprivatekeybytes)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
keyBytes, {[String](../dart-core/string-class)? password}) → void

Sets the private key for a server certificate or client certificate.

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

[alpnSupported](securitycontext/alpnsupported){.deprecated} →
[bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether the platform supports ALPN. This always returns true and will be
removed in a future release.

[defaultContext](securitycontext/defaultcontext) →
[SecurityContext](securitycontext-class)

::: {.features}
read-only
:::

The default security context used by most operation requiring one.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SecurityContext-class.html>
:::
