Package x509
============

-   `import "crypto/x509"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)
-   [Subdirectories](#pkg-subdirectories)

Overview 
--------

Package x509 implements a subset of the X.509 standard.

It allows parsing and generating certificates, certificate signing
requests, certificate revocation lists, and encoded public and private
keys. It provides a certificate verifier, complete with a chain builder.

The package targets the X.509 technical profile defined by the IETF (RFC
2459/3280/5280), and as further restricted by the CA/Browser Forum
Baseline Requirements. There is minimal support for features outside of
these profiles, as the primary goal of the package is to provide
compatibility with the publicly trusted TLS certificate ecosystem and
its policies and constraints.

On macOS and Windows, certificate verification is handled by system
APIs, but the package aims to apply consistent validation rules across
operating systems.

Index 
-----

-   [Variables](#pkg-variables)
-   [func CreateCertificate(rand io.Reader, template, parent
    \*Certificate, pub, priv any) (\[\]byte, error)](#CreateCertificate)
-   [func CreateCertificateRequest(rand io.Reader, template
    \*CertificateRequest, priv any) (csr \[\]byte, err
    error)](#CreateCertificateRequest)
-   [func CreateRevocationList(rand io.Reader, template
    \*RevocationList, issuer \*Certificate, priv crypto.Signer)
    (\[\]byte, error)](#CreateRevocationList)
-   [func DecryptPEMBlock(b \*pem.Block, password \[\]byte) (\[\]byte,
    error)](#DecryptPEMBlock)
-   [func EncryptPEMBlock(rand io.Reader, blockType string, data,
    password \[\]byte, alg PEMCipher) (\*pem.Block,
    error)](#EncryptPEMBlock)
-   [func IsEncryptedPEMBlock(b \*pem.Block) bool](#IsEncryptedPEMBlock)
-   [func MarshalECPrivateKey(key \*ecdsa.PrivateKey) (\[\]byte,
    error)](#MarshalECPrivateKey)
-   [func MarshalPKCS1PrivateKey(key \*rsa.PrivateKey)
    \[\]byte](#MarshalPKCS1PrivateKey)
-   [func MarshalPKCS1PublicKey(key \*rsa.PublicKey)
    \[\]byte](#MarshalPKCS1PublicKey)
-   [func MarshalPKCS8PrivateKey(key any) (\[\]byte,
    error)](#MarshalPKCS8PrivateKey)
-   [func MarshalPKIXPublicKey(pub any) (\[\]byte,
    error)](#MarshalPKIXPublicKey)
-   [func ParseCRL(crlBytes \[\]byte) (\*pkix.CertificateList,
    error)](#ParseCRL)
-   [func ParseDERCRL(derBytes \[\]byte) (\*pkix.CertificateList,
    error)](#ParseDERCRL)
-   [func ParseECPrivateKey(der \[\]byte) (\*ecdsa.PrivateKey,
    error)](#ParseECPrivateKey)
-   [func ParsePKCS1PrivateKey(der \[\]byte) (\*rsa.PrivateKey,
    error)](#ParsePKCS1PrivateKey)
-   [func ParsePKCS1PublicKey(der \[\]byte) (\*rsa.PublicKey,
    error)](#ParsePKCS1PublicKey)
-   [func ParsePKCS8PrivateKey(der \[\]byte) (key any, err
    error)](#ParsePKCS8PrivateKey)
-   [func ParsePKIXPublicKey(derBytes \[\]byte) (pub any, err
    error)](#ParsePKIXPublicKey)
-   [func SetFallbackRoots(roots \*CertPool)](#SetFallbackRoots)
-   [type CertPool](#CertPool)
-   [func NewCertPool() \*CertPool](#NewCertPool)
-   [func SystemCertPool() (\*CertPool, error)](#SystemCertPool)
-   [func (s \*CertPool) AddCert(cert \*Certificate)](#CertPool.AddCert)
-   [func (s \*CertPool) AppendCertsFromPEM(pemCerts \[\]byte) (ok
    bool)](#CertPool.AppendCertsFromPEM)
-   [func (s \*CertPool) Clone() \*CertPool](#CertPool.Clone)
-   [func (s \*CertPool) Equal(other \*CertPool) bool](#CertPool.Equal)
-   [func (s \*CertPool) Subjects() \[\]\[\]byte](#CertPool.Subjects)
-   [type Certificate](#Certificate)
-   [func ParseCertificate(der \[\]byte) (\*Certificate,
    error)](#ParseCertificate)
-   [func ParseCertificates(der \[\]byte) (\[\]\*Certificate,
    error)](#ParseCertificates)
-   [func (c \*Certificate) CheckCRLSignature(crl
    \*pkix.CertificateList) error](#Certificate.CheckCRLSignature)
-   [func (c \*Certificate) CheckSignature(algo SignatureAlgorithm,
    signed, signature \[\]byte) error](#Certificate.CheckSignature)
-   [func (c \*Certificate) CheckSignatureFrom(parent \*Certificate)
    error](#Certificate.CheckSignatureFrom)
-   [func (c \*Certificate) CreateCRL(rand io.Reader, priv any,
    revokedCerts \[\]pkix.RevokedCertificate, now, expiry time.Time)
    (crlBytes \[\]byte, err error)](#Certificate.CreateCRL)
-   [func (c \*Certificate) Equal(other \*Certificate)
    bool](#Certificate.Equal)
-   [func (c \*Certificate) Verify(opts VerifyOptions) (chains
    \[\]\[\]\*Certificate, err error)](#Certificate.Verify)
-   [func (c \*Certificate) VerifyHostname(h string)
    error](#Certificate.VerifyHostname)
-   [type CertificateInvalidError](#CertificateInvalidError)
-   [func (e CertificateInvalidError) Error()
    string](#CertificateInvalidError.Error)
-   [type CertificateRequest](#CertificateRequest)
-   [func ParseCertificateRequest(asn1Data \[\]byte)
    (\*CertificateRequest, error)](#ParseCertificateRequest)
-   [func (c \*CertificateRequest) CheckSignature()
    error](#CertificateRequest.CheckSignature)
-   [type ConstraintViolationError](#ConstraintViolationError)
-   [func (ConstraintViolationError) Error()
    string](#ConstraintViolationError.Error)
-   [type ExtKeyUsage](#ExtKeyUsage)
-   [type HostnameError](#HostnameError)
-   [func (h HostnameError) Error() string](#HostnameError.Error)
-   [type InsecureAlgorithmError](#InsecureAlgorithmError)
-   [func (e InsecureAlgorithmError) Error()
    string](#InsecureAlgorithmError.Error)
-   [type InvalidReason](#InvalidReason)
-   [type KeyUsage](#KeyUsage)
-   [type PEMCipher](#PEMCipher)
-   [type PublicKeyAlgorithm](#PublicKeyAlgorithm)
-   [func (algo PublicKeyAlgorithm) String()
    string](#PublicKeyAlgorithm.String)
-   [type RevocationList](#RevocationList)
-   [func ParseRevocationList(der \[\]byte) (\*RevocationList,
    error)](#ParseRevocationList)
-   [func (rl \*RevocationList) CheckSignatureFrom(parent \*Certificate)
    error](#RevocationList.CheckSignatureFrom)
-   [type RevocationListEntry](#RevocationListEntry)
-   [type SignatureAlgorithm](#SignatureAlgorithm)
-   [func (algo SignatureAlgorithm) String()
    string](#SignatureAlgorithm.String)
-   [type SystemRootsError](#SystemRootsError)
-   [func (se SystemRootsError) Error() string](#SystemRootsError.Error)
-   [func (se SystemRootsError) Unwrap()
    error](#SystemRootsError.Unwrap)
-   [type UnhandledCriticalExtension](#UnhandledCriticalExtension)
-   [func (h UnhandledCriticalExtension) Error()
    string](#UnhandledCriticalExtension.Error)
-   [type UnknownAuthorityError](#UnknownAuthorityError)
-   [func (e UnknownAuthorityError) Error()
    string](#UnknownAuthorityError.Error)
-   [type VerifyOptions](#VerifyOptions)

 
### Examples

[Certificate.Verify](#example_Certificate_Verify)

[ParsePKIXPublicKey](#example_ParsePKIXPublicKey)


### Package files

cert\_pool.go notboring.go parser.go pem\_decrypt.go pkcs1.go pkcs8.go
root.go root\_linux.go root\_unix.go sec1.go verify.go x509.go

Variables 
---------

ErrUnsupportedAlgorithm results from attempting to perform an operation
that involves algorithms that are not currently implemented.

```go
var ErrUnsupportedAlgorithm = errors.New("x509: cannot verify signature: algorithm unimplemented")
```

IncorrectPasswordError is returned when an incorrect password is
detected.

```go
var IncorrectPasswordError = errors.New("x509: decryption password incorrect")
```

func CreateCertificate 
----------------------

```go
func CreateCertificate(rand io.Reader, template, parent *Certificate, pub, priv any) ([]byte, error)
```

CreateCertificate creates a new X.509 v3 certificate based on a
template. The following members of template are currently used:

-   AuthorityKeyId
-   BasicConstraintsValid
-   CRLDistributionPoints
-   DNSNames
-   EmailAddresses
-   ExcludedDNSDomains
-   ExcludedEmailAddresses
-   ExcludedIPRanges
-   ExcludedURIDomains
-   ExtKeyUsage
-   ExtraExtensions
-   IPAddresses
-   IsCA
-   IssuingCertificateURL
-   KeyUsage
-   MaxPathLen
-   MaxPathLenZero
-   NotAfter
-   NotBefore
-   OCSPServer
-   PermittedDNSDomains
-   PermittedDNSDomainsCritical
-   PermittedEmailAddresses
-   PermittedIPRanges
-   PermittedURIDomains
-   PolicyIdentifiers
-   SerialNumber
-   SignatureAlgorithm
-   Subject
-   SubjectKeyId
-   URIs
-   UnknownExtKeyUsage

The certificate is signed by parent. If parent is equal to template then
the certificate is self-signed. The parameter pub is the public key of
the certificate to be generated and priv is the private key of the
signer.

The returned slice is the certificate in DER encoding.

The currently supported key types are \*rsa.PublicKey, \*ecdsa.PublicKey
and ed25519.PublicKey. pub must be a supported key type, and priv must
be a crypto.Signer with a supported public key.

The AuthorityKeyId will be taken from the SubjectKeyId of parent, if
any, unless the resulting certificate is self-signed. Otherwise the
value from template will be used.

If SubjectKeyId from template is empty and the template is a CA,
SubjectKeyId will be generated from the hash of the public key.

func CreateCertificateRequest 
------------------------------------------------------------

```go
func CreateCertificateRequest(rand io.Reader, template *CertificateRequest, priv any) (csr []byte, err error)
```

CreateCertificateRequest creates a new certificate request based on a
template. The following members of template are used:

-   SignatureAlgorithm
-   Subject
-   DNSNames
-   EmailAddresses
-   IPAddresses
-   URIs
-   ExtraExtensions
-   Attributes (deprecated)

priv is the private key to sign the CSR with, and the corresponding
public key will be included in the CSR. It must implement crypto.Signer
and its Public() method must return a \*rsa.PublicKey or a
\*ecdsa.PublicKey or a ed25519.PublicKey. (A \*rsa.PrivateKey,
\*ecdsa.PrivateKey or ed25519.PrivateKey satisfies this.)

The returned slice is the certificate request in DER encoding.

func CreateRevocationList 
----------------------------------------------------------

```go
func CreateRevocationList(rand io.Reader, template *RevocationList, issuer *Certificate, priv crypto.Signer) ([]byte, error)
```

CreateRevocationList creates a new X.509 v2 Certificate Revocation List,
according to RFC 5280, based on template.

The CRL is signed by priv which should be the private key associated
with the public key in the issuer certificate.

The issuer may not be nil, and the crlSign bit must be set in KeyUsage
in order to use it as a CRL issuer.

The issuer distinguished name CRL field and authority key identifier
extension are populated using the issuer certificate. issuer must have
SubjectKeyId set.

func DecryptPEMBlock 
---------------------------------------------------

```go
func DecryptPEMBlock(b *pem.Block, password []byte) ([]byte, error)
```

DecryptPEMBlock takes a PEM block encrypted according to RFC 1423 and
the password used to encrypt it and returns a slice of decrypted DER
encoded bytes. It inspects the DEK-Info header to determine the
algorithm used for decryption. If no DEK-Info header is present, an
error is returned. If an incorrect password is detected an
IncorrectPasswordError is returned. Because of deficiencies in the
format, it\'s not always possible to detect an incorrect password. In
these cases no error will be returned but the decrypted DER bytes will
be random noise.

Deprecated: Legacy PEM encryption as specified in RFC 1423 is insecure
by design. Since it does not authenticate the ciphertext, it is
vulnerable to padding oracle attacks that can let an attacker recover
the plaintext.

func EncryptPEMBlock 
---------------------------------------------------

```go
func EncryptPEMBlock(rand io.Reader, blockType string, data, password []byte, alg PEMCipher) (*pem.Block, error)
```

EncryptPEMBlock returns a PEM block of the specified type holding the
given DER encoded data encrypted with the specified algorithm and
password according to RFC 1423.

Deprecated: Legacy PEM encryption as specified in RFC 1423 is insecure
by design. Since it does not authenticate the ciphertext, it is
vulnerable to padding oracle attacks that can let an attacker recover
the plaintext.

func IsEncryptedPEMBlock 
-------------------------------------------------------

```go
func IsEncryptedPEMBlock(b *pem.Block) bool
```

IsEncryptedPEMBlock returns whether the PEM block is password encrypted
according to RFC 1423.

Deprecated: Legacy PEM encryption as specified in RFC 1423 is insecure
by design. Since it does not authenticate the ciphertext, it is
vulnerable to padding oracle attacks that can let an attacker recover
the plaintext.

func MarshalECPrivateKey 
-------------------------------------------------------

```go
func MarshalECPrivateKey(key *ecdsa.PrivateKey) ([]byte, error)
```

MarshalECPrivateKey converts an EC private key to SEC 1, ASN.1 DER form.

This kind of key is commonly encoded in PEM blocks of type \"EC PRIVATE
KEY\". For a more flexible key format which is not EC specific, use
MarshalPKCS8PrivateKey.

func MarshalPKCS1PrivateKey 
---------------------------

```go
func MarshalPKCS1PrivateKey(key *rsa.PrivateKey) []byte
```

MarshalPKCS1PrivateKey converts an RSA private key to PKCS \#1, ASN.1
DER form.

This kind of key is commonly encoded in PEM blocks of type \"RSA PRIVATE
KEY\". For a more flexible key format which is not RSA specific, use
MarshalPKCS8PrivateKey.

func MarshalPKCS1PublicKey 
-----------------------------------------------------------

```go
func MarshalPKCS1PublicKey(key *rsa.PublicKey) []byte
```

MarshalPKCS1PublicKey converts an RSA public key to PKCS \#1, ASN.1 DER
form.

This kind of key is commonly encoded in PEM blocks of type \"RSA PUBLIC
KEY\".

func MarshalPKCS8PrivateKey 
------------------------------------------------------------

```go
func MarshalPKCS8PrivateKey(key any) ([]byte, error)
```

MarshalPKCS8PrivateKey converts a private key to PKCS \#8, ASN.1 DER
form.

The following key types are currently supported: \*rsa.PrivateKey,
\*ecdsa.PrivateKey, ed25519.PrivateKey (not a pointer), and
\*ecdh.PrivateKey. Unsupported key types result in an error.

This kind of key is commonly encoded in PEM blocks of type \"PRIVATE
KEY\".

func MarshalPKIXPublicKey 
-------------------------

```go
func MarshalPKIXPublicKey(pub any) ([]byte, error)
```

MarshalPKIXPublicKey converts a public key to PKIX, ASN.1 DER form. The
encoded public key is a SubjectPublicKeyInfo structure (see RFC 5280,
Section 4.1).

The following key types are currently supported: \*rsa.PublicKey,
\*ecdsa.PublicKey, ed25519.PublicKey (not a pointer), and
\*ecdh.PublicKey. Unsupported key types result in an error.

This kind of key is commonly encoded in PEM blocks of type \"PUBLIC
KEY\".

func ParseCRL 
-------------

```go
func ParseCRL(crlBytes []byte) (*pkix.CertificateList, error)
```

ParseCRL parses a CRL from the given bytes. It\'s often the case that
PEM encoded CRLs will appear where they should be DER encoded, so this
function will transparently handle PEM encoding as long as there isn\'t
any leading garbage.

Deprecated: Use ParseRevocationList instead.

func ParseDERCRL 
----------------

```go
func ParseDERCRL(derBytes []byte) (*pkix.CertificateList, error)
```

ParseDERCRL parses a DER encoded CRL from the given bytes.

Deprecated: Use ParseRevocationList instead.

func ParseECPrivateKey 
-----------------------------------------------------

```go
func ParseECPrivateKey(der []byte) (*ecdsa.PrivateKey, error)
```

ParseECPrivateKey parses an EC private key in SEC 1, ASN.1 DER form.

This kind of key is commonly encoded in PEM blocks of type \"EC PRIVATE
KEY\".

func ParsePKCS1PrivateKey 
-------------------------

```go
func ParsePKCS1PrivateKey(der []byte) (*rsa.PrivateKey, error)
```

ParsePKCS1PrivateKey parses an RSA private key in PKCS \#1, ASN.1 DER
form.

This kind of key is commonly encoded in PEM blocks of type \"RSA PRIVATE
KEY\".

func ParsePKCS1PublicKey 
---------------------------------------------------------

```go
func ParsePKCS1PublicKey(der []byte) (*rsa.PublicKey, error)
```

ParsePKCS1PublicKey parses an RSA public key in PKCS \#1, ASN.1 DER
form.

This kind of key is commonly encoded in PEM blocks of type \"RSA PUBLIC
KEY\".

func ParsePKCS8PrivateKey 
-------------------------

```go
func ParsePKCS8PrivateKey(der []byte) (key any, err error)
```

ParsePKCS8PrivateKey parses an unencrypted private key in PKCS \#8,
ASN.1 DER form.

It returns a \*rsa.PrivateKey, an \*ecdsa.PrivateKey, an
ed25519.PrivateKey (not a pointer), or an \*ecdh.PrivateKey (for
X25519). More types might be supported in the future.

This kind of key is commonly encoded in PEM blocks of type \"PRIVATE
KEY\".

func ParsePKIXPublicKey 
-----------------------

```go
func ParsePKIXPublicKey(derBytes []byte) (pub any, err error)
```

ParsePKIXPublicKey parses a public key in PKIX, ASN.1 DER form. The
encoded public key is a SubjectPublicKeyInfo structure (see RFC 5280,
Section 4.1).

It returns a \*rsa.PublicKey, \*dsa.PublicKey, \*ecdsa.PublicKey,
ed25519.PublicKey (not a pointer), or \*ecdh.PublicKey (for X25519).
More types might be supported in the future.

This kind of key is commonly encoded in PEM blocks of type \"PUBLIC
KEY\".

#### [Example]

Code:

```go
const pubPEM = `
-----BEGIN PUBLIC KEY-----
MIICIjANBgkqhkiG9w0BAQEFAAOCAg8AMIICCgKCAgEAlRuRnThUjU8/prwYxbty
WPT9pURI3lbsKMiB6Fn/VHOKE13p4D8xgOCADpdRagdT6n4etr9atzDKUSvpMtR3
CP5noNc97WiNCggBjVWhs7szEe8ugyqF23XwpHQ6uV1LKH50m92MbOWfCtjU9p/x
qhNpQQ1AZhqNy5Gevap5k8XzRmjSldNAFZMY7Yv3Gi+nyCwGwpVtBUwhuLzgNFK/
yDtw2WcWmUU7NuC8Q6MWvPebxVtCfVp/iQU6q60yyt6aGOBkhAX0LpKAEhKidixY
nP9PNVBvxgu3XZ4P36gZV6+ummKdBVnc3NqwBLu5+CcdRdusmHPHd5pHf4/38Z3/
6qU2a/fPvWzceVTEgZ47QjFMTCTmCwNt29cvi7zZeQzjtwQgn4ipN9NibRH/Ax/q
TbIzHfrJ1xa2RteWSdFjwtxi9C20HUkjXSeI4YlzQMH0fPX6KCE7aVePTOnB69I/
a9/q96DiXZajwlpq3wFctrs1oXqBp5DVrCIj8hU2wNgB7LtQ1mCtsYz//heai0K9
PhE4X6hiE0YmeAZjR0uHl8M/5aW9xCoJ72+12kKpWAa0SFRWLy6FejNYCYpkupVJ
yecLk/4L1W0l6jQQZnWErXZYe0PNFcmwGXy1Rep83kfBRNKRy5tvocalLlwXLdUk
AIU+2GKjyT3iMuzZxxFxPFMCAwEAAQ==
-----END PUBLIC KEY-----`

block, _ := pem.Decode([]byte(pubPEM))
if block == nil {
    panic("failed to parse PEM block containing the public key")
}

pub, err := x509.ParsePKIXPublicKey(block.Bytes)
if err != nil {
    panic("failed to parse DER encoded public key: " + err.Error())
}

switch pub := pub.(type) {
case *rsa.PublicKey:
    fmt.Println("pub is of type RSA:", pub)
case *dsa.PublicKey:
    fmt.Println("pub is of type DSA:", pub)
case *ecdsa.PublicKey:
    fmt.Println("pub is of type ECDSA:", pub)
case ed25519.PublicKey:
    fmt.Println("pub is of type Ed25519:", pub)
default:
    panic("unknown type of public key")
}
```

func SetFallbackRoots 
------------------------------------------------------

```go
func SetFallbackRoots(roots *CertPool)
```

SetFallbackRoots sets the roots to use during certificate verification,
if no custom roots are specified and a platform verifier or a system
certificate pool is not available (for instance in a container which
does not have a root certificate bundle). SetFallbackRoots will panic if
roots is nil.

SetFallbackRoots may only be called once, if called multiple times it
will panic.

The fallback behavior can be forced on all platforms, even when there is
a system certificate pool, by setting GODEBUG=x509usefallbackroots=1
(note that on Windows and macOS this will disable usage of the platform
verification APIs and cause the pure Go verifier to be used). Setting
x509usefallbackroots=1 without calling SetFallbackRoots has no effect.

type CertPool 
-------------

CertPool is a set of certificates.

```go
type CertPool struct {
    // contains filtered or unexported fields
}
```

### func NewCertPool 

```go
func NewCertPool() *CertPool
```

NewCertPool returns a new, empty CertPool.

### func SystemCertPool 

```go
func SystemCertPool() (*CertPool, error)
```

SystemCertPool returns a copy of the system cert pool.

On Unix systems other than macOS the environment variables
SSL\_CERT\_FILE and SSL\_CERT\_DIR can be used to override the system
default locations for the SSL certificate file and SSL certificate files
directory, respectively. The latter can be a colon-separated list.

Any mutations to the returned pool are not written to disk and do not
affect any other pool returned by SystemCertPool.

New changes in the system cert pool might not be reflected in subsequent
calls.

### func (\*CertPool) AddCert 

```go
func (s *CertPool) AddCert(cert *Certificate)
```

AddCert adds a certificate to a pool.

### func (\*CertPool) AppendCertsFromPEM 

```go
func (s *CertPool) AppendCertsFromPEM(pemCerts []byte) (ok bool)
```

AppendCertsFromPEM attempts to parse a series of PEM encoded
certificates. It appends any certificates found to s and reports whether
any certificates were successfully parsed.

On many Linux systems, /etc/ssl/cert.pem will contain the system wide
set of root CAs in a format suitable for this function.

### func (\*CertPool) Clone 

```go
func (s *CertPool) Clone() *CertPool
```

Clone returns a copy of s.

### func (\*CertPool) Equal 

```go
func (s *CertPool) Equal(other *CertPool) bool
```

Equal reports whether s and other are equal.

### func (\*CertPool) Subjects 

```go
func (s *CertPool) Subjects() [][]byte
```

Subjects returns a list of the DER-encoded subjects of all of the
certificates in the pool.

Deprecated: if s was returned by SystemCertPool, Subjects will not
include the system roots.

type Certificate 
----------------

A Certificate represents an X.509 certificate.

```go
type Certificate struct {
    Raw                     []byte // Complete ASN.1 DER content (certificate, signature algorithm and signature).
    RawTBSCertificate       []byte // Certificate part of raw ASN.1 DER content.
    RawSubjectPublicKeyInfo []byte // DER encoded SubjectPublicKeyInfo.
    RawSubject              []byte // DER encoded Subject
    RawIssuer               []byte // DER encoded Issuer

    Signature          []byte
    SignatureAlgorithm SignatureAlgorithm

    PublicKeyAlgorithm PublicKeyAlgorithm
    PublicKey          any

    Version             int
    SerialNumber        *big.Int
    Issuer              pkix.Name
    Subject             pkix.Name
    NotBefore, NotAfter time.Time // Validity bounds.
    KeyUsage            KeyUsage

    // Extensions contains raw X.509 extensions. When parsing certificates,
    // this can be used to extract non-critical extensions that are not
    // parsed by this package. When marshaling certificates, the Extensions
    // field is ignored, see ExtraExtensions.
    Extensions []pkix.Extension // Go 1.2

    // ExtraExtensions contains extensions to be copied, raw, into any
    // marshaled certificates. Values override any extensions that would
    // otherwise be produced based on the other fields. The ExtraExtensions
    // field is not populated when parsing certificates, see Extensions.
    ExtraExtensions []pkix.Extension // Go 1.2

    // UnhandledCriticalExtensions contains a list of extension IDs that
    // were not (fully) processed when parsing. Verify will fail if this
    // slice is non-empty, unless verification is delegated to an OS
    // library which understands all the critical extensions.
    //
    // Users can access these extensions using Extensions and can remove
    // elements from this slice if they believe that they have been
    // handled.
    UnhandledCriticalExtensions []asn1.ObjectIdentifier // Go 1.5

    ExtKeyUsage        []ExtKeyUsage           // Sequence of extended key usages.
    UnknownExtKeyUsage []asn1.ObjectIdentifier // Encountered extended key usages unknown to this package.

    // BasicConstraintsValid indicates whether IsCA, MaxPathLen,
    // and MaxPathLenZero are valid.
    BasicConstraintsValid bool
    IsCA                  bool

    // MaxPathLen and MaxPathLenZero indicate the presence and
    // value of the BasicConstraints' "pathLenConstraint".
    //
    // When parsing a certificate, a positive non-zero MaxPathLen
    // means that the field was specified, -1 means it was unset,
    // and MaxPathLenZero being true mean that the field was
    // explicitly set to zero. The case of MaxPathLen==0 with MaxPathLenZero==false
    // should be treated equivalent to -1 (unset).
    //
    // When generating a certificate, an unset pathLenConstraint
    // can be requested with either MaxPathLen == -1 or using the
    // zero value for both MaxPathLen and MaxPathLenZero.
    MaxPathLen int
    // MaxPathLenZero indicates that BasicConstraintsValid==true
    // and MaxPathLen==0 should be interpreted as an actual
    // maximum path length of zero. Otherwise, that combination is
    // interpreted as MaxPathLen not being set.
    MaxPathLenZero bool // Go 1.4

    SubjectKeyId   []byte
    AuthorityKeyId []byte

    // RFC 5280, 4.2.2.1 (Authority Information Access)
    OCSPServer            []string // Go 1.2
    IssuingCertificateURL []string // Go 1.2

    // Subject Alternate Name values. (Note that these values may not be valid
    // if invalid values were contained within a parsed certificate. For
    // example, an element of DNSNames may not be a valid DNS domain name.)
    DNSNames       []string
    EmailAddresses []string
    IPAddresses    []net.IP // Go 1.1
    URIs           []*url.URL // Go 1.10

    // Name constraints
    PermittedDNSDomainsCritical bool // if true then the name constraints are marked critical.
    PermittedDNSDomains         []string
    ExcludedDNSDomains          []string // Go 1.9
    PermittedIPRanges           []*net.IPNet // Go 1.10
    ExcludedIPRanges            []*net.IPNet // Go 1.10
    PermittedEmailAddresses     []string // Go 1.10
    ExcludedEmailAddresses      []string // Go 1.10
    PermittedURIDomains         []string // Go 1.10
    ExcludedURIDomains          []string // Go 1.10

    // CRL Distribution Points
    CRLDistributionPoints []string // Go 1.2

    PolicyIdentifiers []asn1.ObjectIdentifier
}
```

### func ParseCertificate 

```go
func ParseCertificate(der []byte) (*Certificate, error)
```

ParseCertificate parses a single certificate from the given ASN.1 DER
data.

### func ParseCertificates 

```go
func ParseCertificates(der []byte) ([]*Certificate, error)
```

ParseCertificates parses one or more certificates from the given ASN.1
DER data. The certificates must be concatenated with no intermediate
padding.

### func (\*Certificate) CheckCRLSignature 

```go
func (c *Certificate) CheckCRLSignature(crl *pkix.CertificateList) error
```

CheckCRLSignature checks that the signature in crl is from c.

Deprecated: Use RevocationList.CheckSignatureFrom instead.

### func (\*Certificate) CheckSignature 

```go
func (c *Certificate) CheckSignature(algo SignatureAlgorithm, signed, signature []byte) error
```

CheckSignature verifies that signature is a valid signature over signed
from c\'s public key.

This is a low-level API that performs no validity checks on the
certificate.

[MD5WithRSA](#MD5WithRSA) signatures are rejected, while
[SHA1WithRSA](#SHA1WithRSA) and [ECDSAWithSHA1](#ECDSAWithSHA1)
signatures are currently accepted.

### func (\*Certificate) CheckSignatureFrom 

```go
func (c *Certificate) CheckSignatureFrom(parent *Certificate) error
```

CheckSignatureFrom verifies that the signature on c is a valid signature
from parent.

This is a low-level API that performs very limited checks, and not a
full path verifier. Most users should use
[Certificate.Verify](#Certificate.Verify) instead.

### func (\*Certificate) CreateCRL 

```go
func (c *Certificate) CreateCRL(rand io.Reader, priv any, revokedCerts []pkix.RevokedCertificate, now, expiry time.Time) (crlBytes []byte, err error)
```

CreateCRL returns a DER encoded CRL, signed by this Certificate, that
contains the given list of revoked certificates.

Deprecated: this method does not generate an RFC 5280 conformant X.509
v2 CRL. To generate a standards compliant CRL, use CreateRevocationList
instead.

### func (\*Certificate) Equal 

```go
func (c *Certificate) Equal(other *Certificate) bool
```

### func (\*Certificate) Verify 

```go
func (c *Certificate) Verify(opts VerifyOptions) (chains [][]*Certificate, err error)
```

Verify attempts to verify c by building one or more chains from c to a
certificate in opts.Roots, using certificates in opts.Intermediates if
needed. If successful, it returns one or more chains where the first
element of the chain is c and the last element is from opts.Roots.

If opts.Roots is nil, the platform verifier might be used, and
verification details might differ from what is described below. If
system roots are unavailable the returned error will be of type
SystemRootsError.

Name constraints in the intermediates will be applied to all names
claimed in the chain, not just opts.DNSName. Thus it is invalid for a
leaf to claim example.com if an intermediate doesn\'t permit it, even if
example.com is not the name being validated. Note that DirectoryName
constraints are not supported.

Name constraint validation follows the rules from RFC 5280, with the
addition that DNS name constraints may use the leading period format
defined for emails and URIs. When a constraint has a leading period it
indicates that at least one additional label must be prepended to the
constrained name to be considered valid.

Extended Key Usage values are enforced nested down a chain, so an
intermediate or root that enumerates EKUs prevents a leaf from asserting
an EKU not in that list. (While this is not specified, it is common
practice in order to limit the types of certificates a CA can issue.)

Certificates that use SHA1WithRSA and ECDSAWithSHA1 signatures are not
supported, and will not be used to build chains.

Certificates other than c in the returned chains should not be modified.

WARNING: this function doesn\'t do any revocation checking.

#### [Example]

Code:

```go
// Verifying with a custom list of root certificates.

const rootPEM = `
-----BEGIN CERTIFICATE-----
MIIEBDCCAuygAwIBAgIDAjppMA0GCSqGSIb3DQEBBQUAMEIxCzAJBgNVBAYTAlVT
MRYwFAYDVQQKEw1HZW9UcnVzdCBJbmMuMRswGQYDVQQDExJHZW9UcnVzdCBHbG9i
YWwgQ0EwHhcNMTMwNDA1MTUxNTU1WhcNMTUwNDA0MTUxNTU1WjBJMQswCQYDVQQG
EwJVUzETMBEGA1UEChMKR29vZ2xlIEluYzElMCMGA1UEAxMcR29vZ2xlIEludGVy
bmV0IEF1dGhvcml0eSBHMjCCASIwDQYJKoZIhvcNAQEBBQADggEPADCCAQoCggEB
AJwqBHdc2FCROgajguDYUEi8iT/xGXAaiEZ+4I/F8YnOIe5a/mENtzJEiaB0C1NP
VaTOgmKV7utZX8bhBYASxF6UP7xbSDj0U/ck5vuR6RXEz/RTDfRK/J9U3n2+oGtv
h8DQUB8oMANA2ghzUWx//zo8pzcGjr1LEQTrfSTe5vn8MXH7lNVg8y5Kr0LSy+rE
ahqyzFPdFUuLH8gZYR/Nnag+YyuENWllhMgZxUYi+FOVvuOAShDGKuy6lyARxzmZ
EASg8GF6lSWMTlJ14rbtCMoU/M4iarNOz0YDl5cDfsCx3nuvRTPPuj5xt970JSXC
DTWJnZ37DhF5iR43xa+OcmkCAwEAAaOB+zCB+DAfBgNVHSMEGDAWgBTAephojYn7
qwVkDBF9qn1luMrMTjAdBgNVHQ4EFgQUSt0GFhu89mi1dvWBtrtiGrpagS8wEgYD
VR0TAQH/BAgwBgEB/wIBADAOBgNVHQ8BAf8EBAMCAQYwOgYDVR0fBDMwMTAvoC2g
K4YpaHR0cDovL2NybC5nZW90cnVzdC5jb20vY3Jscy9ndGdsb2JhbC5jcmwwPQYI
KwYBBQUHAQEEMTAvMC0GCCsGAQUFBzABhiFodHRwOi8vZ3RnbG9iYWwtb2NzcC5n
ZW90cnVzdC5jb20wFwYDVR0gBBAwDjAMBgorBgEEAdZ5AgUBMA0GCSqGSIb3DQEB
BQUAA4IBAQA21waAESetKhSbOHezI6B1WLuxfoNCunLaHtiONgaX4PCVOzf9G0JY
/iLIa704XtE7JW4S615ndkZAkNoUyHgN7ZVm2o6Gb4ChulYylYbc3GrKBIxbf/a/
zG+FA1jDaFETzf3I93k9mTXwVqO94FntT0QJo544evZG0R0SnU++0ED8Vf4GXjza
HFa9llF7b1cq26KqltyMdMKVvvBulRP/F/A8rLIQjcxz++iPAsbw+zOzlTvjwsto
WHPbqCRiOwY1nQ2pM714A5AuTHhdUDqB1O6gyHA43LL5Z/qHQF1hwFGPa4NrzQU6
yuGnBXj8ytqU0CwIPX4WecigUCAkVDNx
-----END CERTIFICATE-----`

const certPEM = `
-----BEGIN CERTIFICATE-----
MIIDujCCAqKgAwIBAgIIE31FZVaPXTUwDQYJKoZIhvcNAQEFBQAwSTELMAkGA1UE
BhMCVVMxEzARBgNVBAoTCkdvb2dsZSBJbmMxJTAjBgNVBAMTHEdvb2dsZSBJbnRl
cm5ldCBBdXRob3JpdHkgRzIwHhcNMTQwMTI5MTMyNzQzWhcNMTQwNTI5MDAwMDAw
WjBpMQswCQYDVQQGEwJVUzETMBEGA1UECAwKQ2FsaWZvcm5pYTEWMBQGA1UEBwwN
TW91bnRhaW4gVmlldzETMBEGA1UECgwKR29vZ2xlIEluYzEYMBYGA1UEAwwPbWFp
bC5nb29nbGUuY29tMFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAEfRrObuSW5T7q
5CnSEqefEmtH4CCv6+5EckuriNr1CjfVvqzwfAhopXkLrq45EQm8vkmf7W96XJhC
7ZM0dYi1/qOCAU8wggFLMB0GA1UdJQQWMBQGCCsGAQUFBwMBBggrBgEFBQcDAjAa
BgNVHREEEzARgg9tYWlsLmdvb2dsZS5jb20wCwYDVR0PBAQDAgeAMGgGCCsGAQUF
BwEBBFwwWjArBggrBgEFBQcwAoYfaHR0cDovL3BraS5nb29nbGUuY29tL0dJQUcy
LmNydDArBggrBgEFBQcwAYYfaHR0cDovL2NsaWVudHMxLmdvb2dsZS5jb20vb2Nz
cDAdBgNVHQ4EFgQUiJxtimAuTfwb+aUtBn5UYKreKvMwDAYDVR0TAQH/BAIwADAf
BgNVHSMEGDAWgBRK3QYWG7z2aLV29YG2u2IaulqBLzAXBgNVHSAEEDAOMAwGCisG
AQQB1nkCBQEwMAYDVR0fBCkwJzAloCOgIYYfaHR0cDovL3BraS5nb29nbGUuY29t
L0dJQUcyLmNybDANBgkqhkiG9w0BAQUFAAOCAQEAH6RYHxHdcGpMpFE3oxDoFnP+
gtuBCHan2yE2GRbJ2Cw8Lw0MmuKqHlf9RSeYfd3BXeKkj1qO6TVKwCh+0HdZk283
TZZyzmEOyclm3UGFYe82P/iDFt+CeQ3NpmBg+GoaVCuWAARJN/KfglbLyyYygcQq
0SgeDh8dRKUiaW3HQSoYvTvdTuqzwK4CXsr3b5/dAOY8uMuG/IAR3FgwTbZ1dtoW
RvOTa8hYiU6A475WuZKyEHcwnGYe57u2I2KbMgcKjPniocj4QzgYsVAVKW3IwaOh
yE+vPxsiUkvQHdO2fojCkY8jg70jxM+gu59tPDNbw3Uh/2Ij310FgTHsnGQMyA==
-----END CERTIFICATE-----`

// First, create the set of root certificates. For this example we only
// have one. It's also possible to omit this in order to use the
// default root set of the current operating system.
roots := x509.NewCertPool()
ok := roots.AppendCertsFromPEM([]byte(rootPEM))
if !ok {
    panic("failed to parse root certificate")
}

block, _ := pem.Decode([]byte(certPEM))
if block == nil {
    panic("failed to parse certificate PEM")
}
cert, err := x509.ParseCertificate(block.Bytes)
if err != nil {
    panic("failed to parse certificate: " + err.Error())
}

opts := x509.VerifyOptions{
    DNSName: "mail.google.com",
    Roots:   roots,
}

if _, err := cert.Verify(opts); err != nil {
    panic("failed to verify certificate: " + err.Error())
}
```

### func (\*Certificate) VerifyHostname 

```go
func (c *Certificate) VerifyHostname(h string) error
```

VerifyHostname returns nil if c is a valid certificate for the named
host. Otherwise it returns an error describing the mismatch.

IP addresses can be optionally enclosed in square brackets and are
checked against the IPAddresses field. Other names are checked case
insensitively against the DNSNames field. If the names are valid
hostnames, the certificate fields can have a wildcard as the complete
left-most label (e.g. \*.example.com).

Note that the legacy Common Name field is ignored.

type CertificateInvalidError 
----------------------------

CertificateInvalidError results when an odd error occurs. Users of this
library probably want to handle all these errors uniformly.

```go
type CertificateInvalidError struct {
    Cert   *Certificate
    Reason InvalidReason
    Detail string // Go 1.10
}
```

### func (CertificateInvalidError) Error 

```go
func (e CertificateInvalidError) Error() string
```

type CertificateRequest 
------------------------------------------------------

CertificateRequest represents a PKCS \#10, certificate signature
request.

```go
type CertificateRequest struct {
    Raw                      []byte // Complete ASN.1 DER content (CSR, signature algorithm and signature).
    RawTBSCertificateRequest []byte // Certificate request info part of raw ASN.1 DER content.
    RawSubjectPublicKeyInfo  []byte // DER encoded SubjectPublicKeyInfo.
    RawSubject               []byte // DER encoded Subject.

    Version            int
    Signature          []byte
    SignatureAlgorithm SignatureAlgorithm

    PublicKeyAlgorithm PublicKeyAlgorithm
    PublicKey          any

    Subject pkix.Name

    // Attributes contains the CSR attributes that can parse as
    // pkix.AttributeTypeAndValueSET.
    //
    // Deprecated: Use Extensions and ExtraExtensions instead for parsing and
    // generating the requestedExtensions attribute.
    Attributes []pkix.AttributeTypeAndValueSET

    // Extensions contains all requested extensions, in raw form. When parsing
    // CSRs, this can be used to extract extensions that are not parsed by this
    // package.
    Extensions []pkix.Extension

    // ExtraExtensions contains extensions to be copied, raw, into any CSR
    // marshaled by CreateCertificateRequest. Values override any extensions
    // that would otherwise be produced based on the other fields but are
    // overridden by any extensions specified in Attributes.
    //
    // The ExtraExtensions field is not populated by ParseCertificateRequest,
    // see Extensions instead.
    ExtraExtensions []pkix.Extension

    // Subject Alternate Name values.
    DNSNames       []string
    EmailAddresses []string
    IPAddresses    []net.IP
    URIs           []*url.URL // Go 1.10
}
```

### func ParseCertificateRequest 

```go
func ParseCertificateRequest(asn1Data []byte) (*CertificateRequest, error)
```

ParseCertificateRequest parses a single certificate request from the
given ASN.1 DER data.

### func (\*CertificateRequest) CheckSignature 

```go
func (c *CertificateRequest) CheckSignature() error
```

CheckSignature reports whether the signature on c is valid.

type ConstraintViolationError 
-----------------------------

ConstraintViolationError results when a requested usage is not permitted
by a certificate. For example: checking a signature when the public key
isn\'t a certificate signing key.

```go
type ConstraintViolationError struct{}
```

### func (ConstraintViolationError) Error 

```go
func (ConstraintViolationError) Error() string
```

type ExtKeyUsage 
----------------

ExtKeyUsage represents an extended set of actions that are valid for a
given key. Each of the ExtKeyUsage\* constants define a unique action.

```go
type ExtKeyUsage int
```

```go
const (
    ExtKeyUsageAny ExtKeyUsage = iota
    ExtKeyUsageServerAuth
    ExtKeyUsageClientAuth
    ExtKeyUsageCodeSigning
    ExtKeyUsageEmailProtection
    ExtKeyUsageIPSECEndSystem
    ExtKeyUsageIPSECTunnel
    ExtKeyUsageIPSECUser
    ExtKeyUsageTimeStamping
    ExtKeyUsageOCSPSigning
    ExtKeyUsageMicrosoftServerGatedCrypto
    ExtKeyUsageNetscapeServerGatedCrypto
    ExtKeyUsageMicrosoftCommercialCodeSigning
    ExtKeyUsageMicrosoftKernelCodeSigning
)
```

type HostnameError 
------------------

HostnameError results when the set of authorized names doesn\'t match
the requested name.

```go
type HostnameError struct {
    Certificate *Certificate
    Host        string
}
```

### func (HostnameError) Error 

```go
func (h HostnameError) Error() string
```

type InsecureAlgorithmError 
----------------------------------------------------------

An InsecureAlgorithmError indicates that the SignatureAlgorithm used to
generate the signature is not secure, and the signature has been
rejected.

To temporarily restore support for SHA-1 signatures, include the value
\"x509sha1=1\" in the GODEBUG environment variable. Note that this
option will be removed in a future release.

```go
type InsecureAlgorithmError SignatureAlgorithm
```

### func (InsecureAlgorithmError) Error 

```go
func (e InsecureAlgorithmError) Error() string
```

type InvalidReason 
------------------

```go
type InvalidReason int
```

```go
const (
    // NotAuthorizedToSign results when a certificate is signed by another
    // which isn't marked as a CA certificate.
    NotAuthorizedToSign InvalidReason = iota
    // Expired results when a certificate has expired, based on the time
    // given in the VerifyOptions.
    Expired
    // CANotAuthorizedForThisName results when an intermediate or root
    // certificate has a name constraint which doesn't permit a DNS or
    // other name (including IP address) in the leaf certificate.
    CANotAuthorizedForThisName
    // TooManyIntermediates results when a path length constraint is
    // violated.
    TooManyIntermediates
    // IncompatibleUsage results when the certificate's key usage indicates
    // that it may only be used for a different purpose.
    IncompatibleUsage
    // NameMismatch results when the subject name of a parent certificate
    // does not match the issuer name in the child.
    NameMismatch
    // NameConstraintsWithoutSANs is a legacy error and is no longer returned.
    NameConstraintsWithoutSANs
    // UnconstrainedName results when a CA certificate contains permitted
    // name constraints, but leaf certificate contains a name of an
    // unsupported or unconstrained type.
    UnconstrainedName
    // TooManyConstraints results when the number of comparison operations
    // needed to check a certificate exceeds the limit set by
    // VerifyOptions.MaxConstraintComparisions. This limit exists to
    // prevent pathological certificates can consuming excessive amounts of
    // CPU time to verify.
    TooManyConstraints
    // CANotAuthorizedForExtKeyUsage results when an intermediate or root
    // certificate does not permit a requested extended key usage.
    CANotAuthorizedForExtKeyUsage
)
```

type KeyUsage 
-------------

KeyUsage represents the set of actions that are valid for a given key.
It\'s a bitmap of the KeyUsage\* constants.

```go
type KeyUsage int
```

```go
const (
    KeyUsageDigitalSignature KeyUsage = 1 << iota
    KeyUsageContentCommitment
    KeyUsageKeyEncipherment
    KeyUsageDataEncipherment
    KeyUsageKeyAgreement
    KeyUsageCertSign
    KeyUsageCRLSign
    KeyUsageEncipherOnly
    KeyUsageDecipherOnly
)
```

type PEMCipher 
---------------------------------------------

```go
type PEMCipher int
```

Possible values for the EncryptPEMBlock encryption algorithm.

```go
const (
    PEMCipherDES PEMCipher
    PEMCipher3DES
    PEMCipherAES128
    PEMCipherAES192
    PEMCipherAES256
)
```

type PublicKeyAlgorithm 
-----------------------

```go
type PublicKeyAlgorithm int
```

```go
const (
    UnknownPublicKeyAlgorithm PublicKeyAlgorithm = iota
    RSA
    DSA // Only supported for parsing.
    ECDSA
    Ed25519
)
```

### func (PublicKeyAlgorithm) String 

```go
func (algo PublicKeyAlgorithm) String() string
```

type RevocationList 
----------------------------------------------------

RevocationList represents a Certificate Revocation List (CRL) as
specified by RFC 5280.

```go
type RevocationList struct {
    // Raw contains the complete ASN.1 DER content of the CRL (tbsCertList,
    // signatureAlgorithm, and signatureValue.)
    Raw []byte // Go 1.19
    // RawTBSRevocationList contains just the tbsCertList portion of the ASN.1
    // DER.
    RawTBSRevocationList []byte // Go 1.19
    // RawIssuer contains the DER encoded Issuer.
    RawIssuer []byte // Go 1.19

    // Issuer contains the DN of the issuing certificate.
    Issuer pkix.Name // Go 1.19
    // AuthorityKeyId is used to identify the public key associated with the
    // issuing certificate. It is populated from the authorityKeyIdentifier
    // extension when parsing a CRL. It is ignored when creating a CRL; the
    // extension is populated from the issuing certificate itself.
    AuthorityKeyId []byte // Go 1.19

    Signature []byte // Go 1.19
    // SignatureAlgorithm is used to determine the signature algorithm to be
    // used when signing the CRL. If 0 the default algorithm for the signing
    // key will be used.
    SignatureAlgorithm SignatureAlgorithm

    // RevokedCertificateEntries represents the revokedCertificates sequence in
    // the CRL. It is used when creating a CRL and also populated when parsing a
    // CRL. When creating a CRL, it may be empty or nil, in which case the
    // revokedCertificates ASN.1 sequence will be omitted from the CRL entirely.
    RevokedCertificateEntries []RevocationListEntry // Go 1.21

    // RevokedCertificates is used to populate the revokedCertificates
    // sequence in the CRL if RevokedCertificateEntries is empty. It may be empty
    // or nil, in which case an empty CRL will be created.
    //
    // Deprecated: Use RevokedCertificateEntries instead.
    RevokedCertificates []pkix.RevokedCertificate

    // Number is used to populate the X.509 v2 cRLNumber extension in the CRL,
    // which should be a monotonically increasing sequence number for a given
    // CRL scope and CRL issuer. It is also populated from the cRLNumber
    // extension when parsing a CRL.
    Number *big.Int

    // ThisUpdate is used to populate the thisUpdate field in the CRL, which
    // indicates the issuance date of the CRL.
    ThisUpdate time.Time
    // NextUpdate is used to populate the nextUpdate field in the CRL, which
    // indicates the date by which the next CRL will be issued. NextUpdate
    // must be greater than ThisUpdate.
    NextUpdate time.Time

    // Extensions contains raw X.509 extensions. When creating a CRL,
    // the Extensions field is ignored, see ExtraExtensions.
    Extensions []pkix.Extension // Go 1.19

    // ExtraExtensions contains any additional extensions to add directly to
    // the CRL.
    ExtraExtensions []pkix.Extension
}
```

### func ParseRevocationList 

```go
func ParseRevocationList(der []byte) (*RevocationList, error)
```

ParseRevocationList parses a X509 v2 Certificate Revocation List from
the given ASN.1 DER data.

### func (\*RevocationList) CheckSignatureFrom 

```go
func (rl *RevocationList) CheckSignatureFrom(parent *Certificate) error
```

CheckSignatureFrom verifies that the signature on rl is a valid
signature from issuer.

type RevocationListEntry 
---------------------------------------------------------

RevocationListEntry represents an entry in the revokedCertificates
sequence of a CRL.

```go
type RevocationListEntry struct {
    // Raw contains the raw bytes of the revokedCertificates entry. It is set when
    // parsing a CRL; it is ignored when generating a CRL.
    Raw []byte

    // SerialNumber represents the serial number of a revoked certificate. It is
    // both used when creating a CRL and populated when parsing a CRL. It must not
    // be nil.
    SerialNumber *big.Int
    // RevocationTime represents the time at which the certificate was revoked. It
    // is both used when creating a CRL and populated when parsing a CRL. It must
    // not be the zero time.
    RevocationTime time.Time
    // ReasonCode represents the reason for revocation, using the integer enum
    // values specified in RFC 5280 Section 5.3.1. When creating a CRL, the zero
    // value will result in the reasonCode extension being omitted. When parsing a
    // CRL, the zero value may represent either the reasonCode extension being
    // absent (which implies the default revocation reason of 0/Unspecified), or
    // it may represent the reasonCode extension being present and explicitly
    // containing a value of 0/Unspecified (which should not happen according to
    // the DER encoding rules, but can and does happen anyway).
    ReasonCode int

    // Extensions contains raw X.509 extensions. When parsing CRL entries,
    // this can be used to extract non-critical extensions that are not
    // parsed by this package. When marshaling CRL entries, the Extensions
    // field is ignored, see ExtraExtensions.
    Extensions []pkix.Extension
    // ExtraExtensions contains extensions to be copied, raw, into any
    // marshaled CRL entries. Values override any extensions that would
    // otherwise be produced based on the other fields. The ExtraExtensions
    // field is not populated when parsing CRL entries, see Extensions.
    ExtraExtensions []pkix.Extension
}
```

type SignatureAlgorithm 
-----------------------

```go
type SignatureAlgorithm int
```

```go
const (
    UnknownSignatureAlgorithm SignatureAlgorithm = iota

    MD2WithRSA  // Unsupported.
    MD5WithRSA  // Only supported for signing, not verification.
    SHA1WithRSA // Only supported for signing, and verification of CRLs, CSRs, and OCSP responses.
    SHA256WithRSA
    SHA384WithRSA
    SHA512WithRSA
    DSAWithSHA1   // Unsupported.
    DSAWithSHA256 // Unsupported.
    ECDSAWithSHA1 // Only supported for signing, and verification of CRLs, CSRs, and OCSP responses.
    ECDSAWithSHA256
    ECDSAWithSHA384
    ECDSAWithSHA512
    SHA256WithRSAPSS
    SHA384WithRSAPSS
    SHA512WithRSAPSS
    PureEd25519
)
```

### func (SignatureAlgorithm) String 

```go
func (algo SignatureAlgorithm) String() string
```

type SystemRootsError 
----------------------------------------------------

SystemRootsError results when we fail to load the system root
certificates.

```go
type SystemRootsError struct {
    Err error // Go 1.7
}
```

### func (SystemRootsError) Error 

```go
func (se SystemRootsError) Error() string
```

### func (SystemRootsError) Unwrap 

```go
func (se SystemRootsError) Unwrap() error
```

type UnhandledCriticalExtension 
-------------------------------

```go
type UnhandledCriticalExtension struct{}
```

### func (UnhandledCriticalExtension) Error 

```go
func (h UnhandledCriticalExtension) Error() string
```

type UnknownAuthorityError 
--------------------------

UnknownAuthorityError results when the certificate issuer is unknown

```go
type UnknownAuthorityError struct {
    Cert *Certificate // Go 1.8
    // contains filtered or unexported fields
}
```

### func (UnknownAuthorityError) Error 

```go
func (e UnknownAuthorityError) Error() string
```

type VerifyOptions 
------------------

VerifyOptions contains parameters for Certificate.Verify.

```go
type VerifyOptions struct {
    // DNSName, if set, is checked against the leaf certificate with
    // Certificate.VerifyHostname or the platform verifier.
    DNSName string

    // Intermediates is an optional pool of certificates that are not trust
    // anchors, but can be used to form a chain from the leaf certificate to a
    // root certificate.
    Intermediates *CertPool
    // Roots is the set of trusted root certificates the leaf certificate needs
    // to chain up to. If nil, the system roots or the platform verifier are used.
    Roots *CertPool

    // CurrentTime is used to check the validity of all certificates in the
    // chain. If zero, the current time is used.
    CurrentTime time.Time

    // KeyUsages specifies which Extended Key Usage values are acceptable. A
    // chain is accepted if it allows any of the listed values. An empty list
    // means ExtKeyUsageServerAuth. To accept any key usage, include ExtKeyUsageAny.
    KeyUsages []ExtKeyUsage // Go 1.1

    // MaxConstraintComparisions is the maximum number of comparisons to
    // perform when checking a given certificate's name constraints. If
    // zero, a sensible default is used. This limit prevents pathological
    // certificates from consuming excessive amounts of CPU time when
    // validating. It does not apply to the platform verifier.
    MaxConstraintComparisions int // Go 1.10
}
```

Subdirectories 
--------------

 
Name


Synopsis

[..](../index)

[pkix](pkix/index)

Package pkix contains shared, low level structures used for ASN.1
parsing and serialization of X.509 certificates, CRL and OCSP.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/crypto/x509/>

