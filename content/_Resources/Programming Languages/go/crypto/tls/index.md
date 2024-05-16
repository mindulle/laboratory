Package tls
===========

- `import "crypto/tls"`
- [Overview](#pkg-overview)
- [Index](#pkg-index)
- [Examples](#pkg-examples)
- [Subdirectories](#pkg-subdirectories)

Overview
--------

Package tls partially implements TLS 1.2, as specified in RFC 5246, and
TLS 1.3, as specified in RFC 8446.

Index
-----

- [Constants](#pkg-constants)
- [func CipherSuiteName(id uint16) string](#CipherSuiteName)
- [func Listen(network, laddr string, config \*Config) (net.Listener,
    error)](#Listen)
- [func NewListener(inner net.Listener, config \*Config)
    net.Listener](#NewListener)
- [func VersionName(version uint16) string](#VersionName)
- [type AlertError](#AlertError)
- [func (e AlertError) Error() string](#AlertError.Error)
- [type Certificate](#Certificate)
- [func LoadX509KeyPair(certFile, keyFile string) (Certificate,
    error)](#LoadX509KeyPair)
- [func X509KeyPair(certPEMBlock, keyPEMBlock \[\]byte) (Certificate,
    error)](#X509KeyPair)
- [type CertificateRequestInfo](#CertificateRequestInfo)
- [func (c \*CertificateRequestInfo) Context()
    context.Context](#CertificateRequestInfo.Context)
- [func (cri \*CertificateRequestInfo) SupportsCertificate(c
    \*Certificate) error](#CertificateRequestInfo.SupportsCertificate)
- [type CertificateVerificationError](#CertificateVerificationError)
- [func (e \*CertificateVerificationError) Error()
    string](#CertificateVerificationError.Error)
- [func (e \*CertificateVerificationError) Unwrap()
    error](#CertificateVerificationError.Unwrap)
- [type CipherSuite](#CipherSuite)
- [func CipherSuites() \[\]\*CipherSuite](#CipherSuites)
- [func InsecureCipherSuites()
    \[\]\*CipherSuite](#InsecureCipherSuites)
- [type ClientAuthType](#ClientAuthType)
- [func (i ClientAuthType) String() string](#ClientAuthType.String)
- [type ClientHelloInfo](#ClientHelloInfo)
- [func (c \*ClientHelloInfo) Context()
    context.Context](#ClientHelloInfo.Context)
- [func (chi \*ClientHelloInfo) SupportsCertificate(c \*Certificate)
    error](#ClientHelloInfo.SupportsCertificate)
- [type ClientSessionCache](#ClientSessionCache)
- [func NewLRUClientSessionCache(capacity int)
    ClientSessionCache](#NewLRUClientSessionCache)
- [type ClientSessionState](#ClientSessionState)
- [func NewResumptionState(ticket \[\]byte, state \*SessionState)
    (\*ClientSessionState, error)](#NewResumptionState)
- [func (cs \*ClientSessionState) ResumptionState() (ticket \[\]byte,
    state \*SessionState, err
    error)](#ClientSessionState.ResumptionState)
- [type Config](#Config)
- [func (c \*Config)
    BuildNameToCertificate()](#Config.BuildNameToCertificate)
- [func (c \*Config) Clone() \*Config](#Config.Clone)
- [func (c \*Config) DecryptTicket(identity \[\]byte, cs
    ConnectionState) (\*SessionState, error)](#Config.DecryptTicket)
- [func (c \*Config) EncryptTicket(cs ConnectionState, ss
    \*SessionState) (\[\]byte, error)](#Config.EncryptTicket)
- [func (c \*Config) SetSessionTicketKeys(keys
    \[\]\[32\]byte)](#Config.SetSessionTicketKeys)
- [type Conn](#Conn)
- [func Client(conn net.Conn, config \*Config) \*Conn](#Client)
- [func Dial(network, addr string, config \*Config) (\*Conn,
    error)](#Dial)
- [func DialWithDialer(dialer \*net.Dialer, network, addr string,
    config \*Config) (\*Conn, error)](#DialWithDialer)
- [func Server(conn net.Conn, config \*Config) \*Conn](#Server)
- [func (c \*Conn) Close() error](#Conn.Close)
- [func (c \*Conn) CloseWrite() error](#Conn.CloseWrite)
- [func (c \*Conn) ConnectionState()
    ConnectionState](#Conn.ConnectionState)
- [func (c \*Conn) Handshake() error](#Conn.Handshake)
- [func (c \*Conn) HandshakeContext(ctx context.Context)
    error](#Conn.HandshakeContext)
- [func (c \*Conn) LocalAddr() net.Addr](#Conn.LocalAddr)
- [func (c \*Conn) NetConn() net.Conn](#Conn.NetConn)
- [func (c \*Conn) OCSPResponse() \[\]byte](#Conn.OCSPResponse)
- [func (c \*Conn) Read(b \[\]byte) (int, error)](#Conn.Read)
- [func (c \*Conn) RemoteAddr() net.Addr](#Conn.RemoteAddr)
- [func (c \*Conn) SetDeadline(t time.Time) error](#Conn.SetDeadline)
- [func (c \*Conn) SetReadDeadline(t time.Time)
    error](#Conn.SetReadDeadline)
- [func (c \*Conn) SetWriteDeadline(t time.Time)
    error](#Conn.SetWriteDeadline)
- [func (c \*Conn) VerifyHostname(host string)
    error](#Conn.VerifyHostname)
- [func (c \*Conn) Write(b \[\]byte) (int, error)](#Conn.Write)
- [type ConnectionState](#ConnectionState)
- [func (cs \*ConnectionState) ExportKeyingMaterial(label string,
    context \[\]byte, length int) (\[\]byte,
    error)](#ConnectionState.ExportKeyingMaterial)
- [type CurveID](#CurveID)
- [func (i CurveID) String() string](#CurveID.String)
- [type Dialer](#Dialer)
- [func (d \*Dialer) Dial(network, addr string) (net.Conn,
    error)](#Dialer.Dial)
- [func (d \*Dialer) DialContext(ctx context.Context, network, addr
    string) (net.Conn, error)](#Dialer.DialContext)
- [type QUICConfig](#QUICConfig)
- [type QUICConn](#QUICConn)
- [func QUICClient(config \*QUICConfig) \*QUICConn](#QUICClient)
- [func QUICServer(config \*QUICConfig) \*QUICConn](#QUICServer)
- [func (q \*QUICConn) Close() error](#QUICConn.Close)
- [func (q \*QUICConn) ConnectionState()
    ConnectionState](#QUICConn.ConnectionState)
- [func (q \*QUICConn) HandleData(level QUICEncryptionLevel, data
    \[\]byte) error](#QUICConn.HandleData)
- [func (q \*QUICConn) NextEvent() QUICEvent](#QUICConn.NextEvent)
- [func (q \*QUICConn) SendSessionTicket(opts
    QUICSessionTicketOptions) error](#QUICConn.SendSessionTicket)
- [func (q \*QUICConn) SetTransportParameters(params
    \[\]byte)](#QUICConn.SetTransportParameters)
- [func (q \*QUICConn) Start(ctx context.Context)
    error](#QUICConn.Start)
- [type QUICEncryptionLevel](#QUICEncryptionLevel)
- [func (l QUICEncryptionLevel) String()
    string](#QUICEncryptionLevel.String)
- [type QUICEvent](#QUICEvent)
- [type QUICEventKind](#QUICEventKind)
- [type QUICSessionTicketOptions](#QUICSessionTicketOptions)
- [type RecordHeaderError](#RecordHeaderError)
- [func (e RecordHeaderError) Error()
    string](#RecordHeaderError.Error)
- [type RenegotiationSupport](#RenegotiationSupport)
- [type SessionState](#SessionState)
- [func ParseSessionState(data \[\]byte) (\*SessionState,
    error)](#ParseSessionState)
- [func (s \*SessionState) Bytes() (\[\]byte,
    error)](#SessionState.Bytes)
- [type SignatureScheme](#SignatureScheme)
- [func (i SignatureScheme) String() string](#SignatureScheme.String)
- [Bugs](#pkg-note-BUG)

### Examples

[Config (KeyLogWriter)](#example_Config_keyLogWriter)

[Config
(VerifyConnection)](#example_Config_verifyConnection)

[Dial](#example_Dial)

[LoadX509KeyPair](#example_LoadX509KeyPair)

[X509KeyPair](#example_X509KeyPair)

[X509KeyPair
(HttpServer)](#example_X509KeyPair_httpServer)

### Package files

alert.go auth.go cache.go cipher\_suites.go common.go common\_string.go
conn.go handshake\_client.go handshake\_client\_tls13.go
handshake\_messages.go handshake\_server.go handshake\_server\_tls13.go
key\_agreement.go key\_schedule.go notboring.go prf.go quic.go ticket.go
tls.go

Constants
---------

A list of cipher suite IDs that are, or have been, implemented by this
package.

See https://www.iana.org/assignments/tls-parameters/tls-parameters.xml>

```go
const (
    // TLS 1.0 - 1.2 cipher suites.
    TLS_RSA_WITH_RC4_128_SHA                      uint16 = 0x0005
    TLS_RSA_WITH_3DES_EDE_CBC_SHA                 uint16 = 0x000a
    TLS_RSA_WITH_AES_128_CBC_SHA                  uint16 = 0x002f
    TLS_RSA_WITH_AES_256_CBC_SHA                  uint16 = 0x0035
    TLS_RSA_WITH_AES_128_CBC_SHA256               uint16 = 0x003c
    TLS_RSA_WITH_AES_128_GCM_SHA256               uint16 = 0x009c
    TLS_RSA_WITH_AES_256_GCM_SHA384               uint16 = 0x009d
    TLS_ECDHE_ECDSA_WITH_RC4_128_SHA              uint16 = 0xc007
    TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA          uint16 = 0xc009
    TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA          uint16 = 0xc00a
    TLS_ECDHE_RSA_WITH_RC4_128_SHA                uint16 = 0xc011
    TLS_ECDHE_RSA_WITH_3DES_EDE_CBC_SHA           uint16 = 0xc012
    TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA            uint16 = 0xc013
    TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA            uint16 = 0xc014
    TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256       uint16 = 0xc023
    TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256         uint16 = 0xc027
    TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256         uint16 = 0xc02f
    TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256       uint16 = 0xc02b
    TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384         uint16 = 0xc030
    TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384       uint16 = 0xc02c
    TLS_ECDHE_RSA_WITH_CHACHA20_POLY1305_SHA256   uint16 = 0xcca8
    TLS_ECDHE_ECDSA_WITH_CHACHA20_POLY1305_SHA256 uint16 = 0xcca9

    // TLS 1.3 cipher suites.
    TLS_AES_128_GCM_SHA256       uint16 = 0x1301
    TLS_AES_256_GCM_SHA384       uint16 = 0x1302
    TLS_CHACHA20_POLY1305_SHA256 uint16 = 0x1303

    // TLS_FALLBACK_SCSV isn't a standard cipher suite but an indicator
    // that the client is doing version fallback. See RFC 7507.
    TLS_FALLBACK_SCSV uint16 = 0x5600

    // Legacy names for the corresponding cipher suites with the correct _SHA256
    // suffix, retained for backward compatibility.
    TLS_ECDHE_RSA_WITH_CHACHA20_POLY1305   = TLS_ECDHE_RSA_WITH_CHACHA20_POLY1305_SHA256
    TLS_ECDHE_ECDSA_WITH_CHACHA20_POLY1305 = TLS_ECDHE_ECDSA_WITH_CHACHA20_POLY1305_SHA256
)
```

```go
const (
    VersionTLS10 = 0x0301
    VersionTLS11 = 0x0302
    VersionTLS12 = 0x0303
    VersionTLS13 = 0x0304

    // Deprecated: SSLv3 is cryptographically broken, and is no longer
    // supported by this package. See golang.org/issue/32716.
    VersionSSL30 = 0x0300
)
```

```go
const (
    QUICEncryptionLevelInitial = QUICEncryptionLevel(iota)
    QUICEncryptionLevelEarly
    QUICEncryptionLevelHandshake
    QUICEncryptionLevelApplication
)
```

func CipherSuiteName
-----------------------------------------------------

```go
func CipherSuiteName(id uint16) string
```

CipherSuiteName returns the standard name for the passed cipher suite ID
(e.g. \"TLS\_ECDHE\_ECDSA\_WITH\_AES\_128\_GCM\_SHA256\"), or a fallback
representation of the ID value if the cipher suite is not implemented by
this package.

func Listen
-----------

```go
func Listen(network, laddr string, config *Config) (net.Listener, error)
```

Listen creates a TLS listener accepting connections on the given network
address using net.Listen. The configuration config must be non-nil and
must include at least one certificate or else set GetCertificate.

func NewListener
----------------

```go
func NewListener(inner net.Listener, config *Config) net.Listener
```

NewListener creates a Listener which accepts connections from an inner
Listener and wraps each connection with Server. The configuration config
must be non-nil and must include at least one certificate or else set
GetCertificate.

func VersionName
-------------------------------------------------

```go
func VersionName(version uint16) string
```

VersionName returns the name for the provided TLS version number (e.g.
\"TLS 1.3\"), or a fallback representation of the value if the version
is not implemented by this package.

type AlertError
------------------------------------------------

An AlertError is a TLS alert.

When using a QUIC transport, QUICConn methods will return an error which
wraps AlertError rather than sending a TLS alert.

```go
type AlertError uint8
```

### func (AlertError) Error

```go
func (e AlertError) Error() string
```

type Certificate
----------------

A Certificate is a chain of one or more certificates, leaf first.

```go
type Certificate struct {
    Certificate [][]byte
    // PrivateKey contains the private key corresponding to the public key in
    // Leaf. This must implement crypto.Signer with an RSA, ECDSA or Ed25519 PublicKey.
    // For a server up to TLS 1.2, it can also implement crypto.Decrypter with
    // an RSA PublicKey.
    PrivateKey crypto.PrivateKey
    // SupportedSignatureAlgorithms is an optional list restricting what
    // signature algorithms the PrivateKey can be used for.
    SupportedSignatureAlgorithms []SignatureScheme // Go 1.14
    // OCSPStaple contains an optional OCSP response which will be served
    // to clients that request it.
    OCSPStaple []byte
    // SignedCertificateTimestamps contains an optional list of Signed
    // Certificate Timestamps which will be served to clients that request it.
    SignedCertificateTimestamps [][]byte // Go 1.5
    // Leaf is the parsed form of the leaf certificate, which may be initialized
    // using x509.ParseCertificate to reduce per-handshake processing. If nil,
    // the leaf certificate will be parsed as needed.
    Leaf *x509.Certificate
}
```

### func LoadX509KeyPair

```go
func LoadX509KeyPair(certFile, keyFile string) (Certificate, error)
```

LoadX509KeyPair reads and parses a public/private key pair from a pair
of files. The files must contain PEM encoded data. The certificate file
may contain intermediate certificates following the leaf certificate to
form a certificate chain. On successful return, Certificate.Leaf will be
nil because the parsed form of the certificate is not retained.

#### [Example]

Code:

```go
cert, err := tls.LoadX509KeyPair("testdata/example-cert.pem", "testdata/example-key.pem")
if err != nil {
    log.Fatal(err)
}
cfg := &tls.Config{Certificates: []tls.Certificate{cert}}
listener, err := tls.Listen("tcp", ":2000", cfg)
if err != nil {
    log.Fatal(err)
}
_ = listener
```

### func X509KeyPair

```go
func X509KeyPair(certPEMBlock, keyPEMBlock []byte) (Certificate, error)
```

X509KeyPair parses a public/private key pair from a pair of PEM encoded
data. On successful return, Certificate.Leaf will be nil because the
parsed form of the certificate is not retained.

#### [Example]

Code:

```go
certPem := []byte(`-----BEGIN CERTIFICATE-----
MIIBhTCCASugAwIBAgIQIRi6zePL6mKjOipn+dNuaTAKBggqhkjOPQQDAjASMRAw
DgYDVQQKEwdBY21lIENvMB4XDTE3MTAyMDE5NDMwNloXDTE4MTAyMDE5NDMwNlow
EjEQMA4GA1UEChMHQWNtZSBDbzBZMBMGByqGSM49AgEGCCqGSM49AwEHA0IABD0d
7VNhbWvZLWPuj/RtHFjvtJBEwOkhbN/BnnE8rnZR8+sbwnc/KhCk3FhnpHZnQz7B
5aETbbIgmuvewdjvSBSjYzBhMA4GA1UdDwEB/wQEAwICpDATBgNVHSUEDDAKBggr
BgEFBQcDATAPBgNVHRMBAf8EBTADAQH/MCkGA1UdEQQiMCCCDmxvY2FsaG9zdDo1
NDUzgg4xMjcuMC4wLjE6NTQ1MzAKBggqhkjOPQQDAgNIADBFAiEA2zpJEPQyz6/l
Wf86aX6PepsntZv2GYlA5UpabfT2EZICICpJ5h/iI+i341gBmLiAFQOyTDT+/wQc
6MF9+Yw1Yy0t
-----END CERTIFICATE-----`)
keyPem := []byte(`-----BEGIN EC PRIVATE KEY-----
MHcCAQEEIIrYSSNQFaA2Hwf1duRSxKtLYX5CB04fSeQ6tF1aY/PuoAoGCCqGSM49
AwEHoUQDQgAEPR3tU2Fta9ktY+6P9G0cWO+0kETA6SFs38GecTyudlHz6xvCdz8q
EKTcWGekdmdDPsHloRNtsiCa697B2O9IFA==
-----END EC PRIVATE KEY-----`)
cert, err := tls.X509KeyPair(certPem, keyPem)
if err != nil {
    log.Fatal(err)
}
cfg := &tls.Config{Certificates: []tls.Certificate{cert}}
listener, err := tls.Listen("tcp", ":2000", cfg)
if err != nil {
    log.Fatal(err)
}
_ = listener
```

#### [Example (HttpServer)]

Code:

```go
certPem := []byte(`-----BEGIN CERTIFICATE-----
MIIBhTCCASugAwIBAgIQIRi6zePL6mKjOipn+dNuaTAKBggqhkjOPQQDAjASMRAw
DgYDVQQKEwdBY21lIENvMB4XDTE3MTAyMDE5NDMwNloXDTE4MTAyMDE5NDMwNlow
EjEQMA4GA1UEChMHQWNtZSBDbzBZMBMGByqGSM49AgEGCCqGSM49AwEHA0IABD0d
7VNhbWvZLWPuj/RtHFjvtJBEwOkhbN/BnnE8rnZR8+sbwnc/KhCk3FhnpHZnQz7B
5aETbbIgmuvewdjvSBSjYzBhMA4GA1UdDwEB/wQEAwICpDATBgNVHSUEDDAKBggr
BgEFBQcDATAPBgNVHRMBAf8EBTADAQH/MCkGA1UdEQQiMCCCDmxvY2FsaG9zdDo1
NDUzgg4xMjcuMC4wLjE6NTQ1MzAKBggqhkjOPQQDAgNIADBFAiEA2zpJEPQyz6/l
Wf86aX6PepsntZv2GYlA5UpabfT2EZICICpJ5h/iI+i341gBmLiAFQOyTDT+/wQc
6MF9+Yw1Yy0t
-----END CERTIFICATE-----`)
keyPem := []byte(`-----BEGIN EC PRIVATE KEY-----
MHcCAQEEIIrYSSNQFaA2Hwf1duRSxKtLYX5CB04fSeQ6tF1aY/PuoAoGCCqGSM49
AwEHoUQDQgAEPR3tU2Fta9ktY+6P9G0cWO+0kETA6SFs38GecTyudlHz6xvCdz8q
EKTcWGekdmdDPsHloRNtsiCa697B2O9IFA==
-----END EC PRIVATE KEY-----`)
cert, err := tls.X509KeyPair(certPem, keyPem)
if err != nil {
    log.Fatal(err)
}
cfg := &tls.Config{Certificates: []tls.Certificate{cert}}
srv := &http.Server{
    TLSConfig:    cfg,
    ReadTimeout:  time.Minute,
    WriteTimeout: time.Minute,
}
log.Fatal(srv.ListenAndServeTLS("", ""))
```

type CertificateRequestInfo
----------------------------------------------------------

CertificateRequestInfo contains information from a server\'s
CertificateRequest message, which is used to demand a certificate and
proof of control from a client.

```go
type CertificateRequestInfo struct {
    // AcceptableCAs contains zero or more, DER-encoded, X.501
    // Distinguished Names. These are the names of root or intermediate CAs
    // that the server wishes the returned certificate to be signed by. An
    // empty slice indicates that the server has no preference.
    AcceptableCAs [][]byte

    // SignatureSchemes lists the signature schemes that the server is
    // willing to verify.
    SignatureSchemes []SignatureScheme

    // Version is the TLS version that was negotiated for this connection.
    Version uint16 // Go 1.14
    // contains filtered or unexported fields
}
```

### func (\*CertificateRequestInfo) Context

```go
func (c *CertificateRequestInfo) Context() context.Context
```

Context returns the context of the handshake that is in progress. This
context is a child of the context passed to HandshakeContext, if any,
and is canceled when the handshake concludes.

### func (\*CertificateRequestInfo) SupportsCertificate

```go
func (cri *CertificateRequestInfo) SupportsCertificate(c *Certificate) error
```

SupportsCertificate returns nil if the provided certificate is supported
by the server that sent the CertificateRequest. Otherwise, it returns an
error describing the reason for the incompatibility.

type CertificateVerificationError
------------------------------------------------------------------

CertificateVerificationError is returned when certificate verification
fails during the handshake.

```go
type CertificateVerificationError struct {
    // UnverifiedCertificates and its contents should not be modified.
    UnverifiedCertificates []*x509.Certificate
    Err                    error
}
```

### func (\*CertificateVerificationError) Error

```go
func (e *CertificateVerificationError) Error() string
```

### func (\*CertificateVerificationError) Unwrap

```go
func (e *CertificateVerificationError) Unwrap() error
```

type CipherSuite
-------------------------------------------------

CipherSuite is a TLS cipher suite. Note that most functions in this
package accept and expose cipher suite IDs instead of this type.

```go
type CipherSuite struct {
    ID   uint16
    Name string

    // Supported versions is the list of TLS protocol versions that can
    // negotiate this cipher suite.
    SupportedVersions []uint16

    // Insecure is true if the cipher suite has known security issues
    // due to its primitives, design, or implementation.
    Insecure bool
}
```

### func CipherSuites

```go
func CipherSuites() []*CipherSuite
```

CipherSuites returns a list of cipher suites currently implemented by
this package, excluding those with security issues, which are returned
by InsecureCipherSuites.

The list is sorted by ID. Note that the default cipher suites selected
by this package might depend on logic that can\'t be captured by a
static list, and might not match those returned by this function.

### func InsecureCipherSuites

```go
func InsecureCipherSuites() []*CipherSuite
```

InsecureCipherSuites returns a list of cipher suites currently
implemented by this package and which have security issues.

Most applications should not use the cipher suites in this list, and
should only use those returned by CipherSuites.

type ClientAuthType
-------------------

ClientAuthType declares the policy the server will follow for TLS Client
Authentication.

```go
type ClientAuthType int
```

```go
const (
    // NoClientCert indicates that no client certificate should be requested
    // during the handshake, and if any certificates are sent they will not
    // be verified.
    NoClientCert ClientAuthType = iota
    // RequestClientCert indicates that a client certificate should be requested
    // during the handshake, but does not require that the client send any
    // certificates.
    RequestClientCert
    // RequireAnyClientCert indicates that a client certificate should be requested
    // during the handshake, and that at least one certificate is required to be
    // sent by the client, but that certificate is not required to be valid.
    RequireAnyClientCert
    // VerifyClientCertIfGiven indicates that a client certificate should be requested
    // during the handshake, but does not require that the client sends a
    // certificate. If the client does send a certificate it is required to be
    // valid.
    VerifyClientCertIfGiven
    // RequireAndVerifyClientCert indicates that a client certificate should be requested
    // during the handshake, and that at least one valid certificate is required
    // to be sent by the client.
    RequireAndVerifyClientCert
)
```

### func (ClientAuthType) String

```go
func (i ClientAuthType) String() string
```

type ClientHelloInfo
---------------------------------------------------

ClientHelloInfo contains information from a ClientHello message in order
to guide application logic in the GetCertificate and GetConfigForClient
callbacks.

```go
type ClientHelloInfo struct {
    // CipherSuites lists the CipherSuites supported by the client (e.g.
    // TLS_AES_128_GCM_SHA256, TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256).
    CipherSuites []uint16

    // ServerName indicates the name of the server requested by the client
    // in order to support virtual hosting. ServerName is only set if the
    // client is using SNI (see RFC 4366, Section 3.1).
    ServerName string

    // SupportedCurves lists the elliptic curves supported by the client.
    // SupportedCurves is set only if the Supported Elliptic Curves
    // Extension is being used (see RFC 4492, Section 5.1.1).
    SupportedCurves []CurveID

    // SupportedPoints lists the point formats supported by the client.
    // SupportedPoints is set only if the Supported Point Formats Extension
    // is being used (see RFC 4492, Section 5.1.2).
    SupportedPoints []uint8

    // SignatureSchemes lists the signature and hash schemes that the client
    // is willing to verify. SignatureSchemes is set only if the Signature
    // Algorithms Extension is being used (see RFC 5246, Section 7.4.1.4.1).
    SignatureSchemes []SignatureScheme // Go 1.8

    // SupportedProtos lists the application protocols supported by the client.
    // SupportedProtos is set only if the Application-Layer Protocol
    // Negotiation Extension is being used (see RFC 7301, Section 3.1).
    //
    // Servers can select a protocol by setting Config.NextProtos in a
    // GetConfigForClient return value.
    SupportedProtos []string // Go 1.8

    // SupportedVersions lists the TLS versions supported by the client.
    // For TLS versions less than 1.3, this is extrapolated from the max
    // version advertised by the client, so values other than the greatest
    // might be rejected if used.
    SupportedVersions []uint16 // Go 1.8

    // Conn is the underlying net.Conn for the connection. Do not read
    // from, or write to, this connection; that will cause the TLS
    // connection to fail.
    Conn net.Conn // Go 1.8
    // contains filtered or unexported fields
}
```

### func (\*ClientHelloInfo) Context

```go
func (c *ClientHelloInfo) Context() context.Context
```

Context returns the context of the handshake that is in progress. This
context is a child of the context passed to HandshakeContext, if any,
and is canceled when the handshake concludes.

### func (\*ClientHelloInfo) SupportsCertificate

```go
func (chi *ClientHelloInfo) SupportsCertificate(c *Certificate) error
```

SupportsCertificate returns nil if the provided certificate is supported
by the client that sent the ClientHello. Otherwise, it returns an error
describing the reason for the incompatibility.

If this ClientHelloInfo was passed to a GetConfigForClient or
GetCertificate callback, this method will take into account the
associated Config. Note that if GetConfigForClient returns a different
Config, the change can\'t be accounted for by this method.

This function will call x509.ParseCertificate unless c.Leaf is set,
which can incur a significant performance cost.

type ClientSessionCache
------------------------------------------------------

ClientSessionCache is a cache of ClientSessionState objects that can be
used by a client to resume a TLS session with a given server.
ClientSessionCache implementations should expect to be called
concurrently from different goroutines. Up to TLS 1.2, only ticket-based
resumption is supported, not SessionID-based resumption. In TLS 1.3 they
were merged into PSK modes, which are supported via this interface.

```go
type ClientSessionCache interface {
    // Get searches for a ClientSessionState associated with the given key.
    // On return, ok is true if one was found.
    Get(sessionKey string) (session *ClientSessionState, ok bool)

    // Put adds the ClientSessionState to the cache with the given key. It might
    // get called multiple times in a connection if a TLS 1.3 server provides
    // more than one session ticket. If called with a nil *ClientSessionState,
    // it should remove the cache entry.
    Put(sessionKey string, cs *ClientSessionState)
}
```

### func NewLRUClientSessionCache

```go
func NewLRUClientSessionCache(capacity int) ClientSessionCache
```

NewLRUClientSessionCache returns a ClientSessionCache with the given
capacity that uses an LRU strategy. If capacity is \< 1, a default
capacity is used instead.

type ClientSessionState
------------------------------------------------------

ClientSessionState contains the state needed by a client to resume a
previous TLS session.

```go
type ClientSessionState struct {
    // contains filtered or unexported fields
}
```

### func NewResumptionState

```go
func NewResumptionState(ticket []byte, state *SessionState) (*ClientSessionState, error)
```

NewResumptionState returns a state value that can be returned by
\[ClientSessionCache.Get\] to resume a previous session.

state needs to be returned by [ParseSessionState](#ParseSessionState),
and the ticket and session state must have been returned by
[ClientSessionState.ResumptionState](#ClientSessionState.ResumptionState).

### func (\*ClientSessionState) ResumptionState

```go
func (cs *ClientSessionState) ResumptionState() (ticket []byte, state *SessionState, err error)
```

ResumptionState returns the session ticket sent by the server (also
known as the session\'s identity) and the state necessary to resume this
session.

It can be called by \[ClientSessionCache.Put\] to serialize (with
[SessionState.Bytes](#SessionState.Bytes)) and store the session.

type Config
-----------

A Config structure is used to configure a TLS client or server. After
one has been passed to a TLS function it must not be modified. A Config
may be reused; the tls package will also not modify it.

```go
type Config struct {
    // Rand provides the source of entropy for nonces and RSA blinding.
    // If Rand is nil, TLS uses the cryptographic random reader in package
    // crypto/rand.
    // The Reader must be safe for use by multiple goroutines.
    Rand io.Reader

    // Time returns the current time as the number of seconds since the epoch.
    // If Time is nil, TLS uses time.Now.
    Time func() time.Time

    // Certificates contains one or more certificate chains to present to the
    // other side of the connection. The first certificate compatible with the
    // peer's requirements is selected automatically.
    //
    // Server configurations must set one of Certificates, GetCertificate or
    // GetConfigForClient. Clients doing client-authentication may set either
    // Certificates or GetClientCertificate.
    //
    // Note: if there are multiple Certificates, and they don't have the
    // optional field Leaf set, certificate selection will incur a significant
    // per-handshake performance cost.
    Certificates []Certificate

    // NameToCertificate maps from a certificate name to an element of
    // Certificates. Note that a certificate name can be of the form
    // '*.example.com' and so doesn't have to be a domain name as such.
    //
    // Deprecated: NameToCertificate only allows associating a single
    // certificate with a given name. Leave this field nil to let the library
    // select the first compatible chain from Certificates.
    NameToCertificate map[string]*Certificate

    // GetCertificate returns a Certificate based on the given
    // ClientHelloInfo. It will only be called if the client supplies SNI
    // information or if Certificates is empty.
    //
    // If GetCertificate is nil or returns nil, then the certificate is
    // retrieved from NameToCertificate. If NameToCertificate is nil, the
    // best element of Certificates will be used.
    //
    // Once a Certificate is returned it should not be modified.
    GetCertificate func(*ClientHelloInfo) (*Certificate, error) // Go 1.4

    // GetClientCertificate, if not nil, is called when a server requests a
    // certificate from a client. If set, the contents of Certificates will
    // be ignored.
    //
    // If GetClientCertificate returns an error, the handshake will be
    // aborted and that error will be returned. Otherwise
    // GetClientCertificate must return a non-nil Certificate. If
    // Certificate.Certificate is empty then no certificate will be sent to
    // the server. If this is unacceptable to the server then it may abort
    // the handshake.
    //
    // GetClientCertificate may be called multiple times for the same
    // connection if renegotiation occurs or if TLS 1.3 is in use.
    //
    // Once a Certificate is returned it should not be modified.
    GetClientCertificate func(*CertificateRequestInfo) (*Certificate, error) // Go 1.8

    // GetConfigForClient, if not nil, is called after a ClientHello is
    // received from a client. It may return a non-nil Config in order to
    // change the Config that will be used to handle this connection. If
    // the returned Config is nil, the original Config will be used. The
    // Config returned by this callback may not be subsequently modified.
    //
    // If GetConfigForClient is nil, the Config passed to Server() will be
    // used for all connections.
    //
    // If SessionTicketKey was explicitly set on the returned Config, or if
    // SetSessionTicketKeys was called on the returned Config, those keys will
    // be used. Otherwise, the original Config keys will be used (and possibly
    // rotated if they are automatically managed).
    GetConfigForClient func(*ClientHelloInfo) (*Config, error) // Go 1.8

    // VerifyPeerCertificate, if not nil, is called after normal
    // certificate verification by either a TLS client or server. It
    // receives the raw ASN.1 certificates provided by the peer and also
    // any verified chains that normal processing found. If it returns a
    // non-nil error, the handshake is aborted and that error results.
    //
    // If normal verification fails then the handshake will abort before
    // considering this callback. If normal verification is disabled (on the
    // client when InsecureSkipVerify is set, or on a server when ClientAuth is
    // RequestClientCert or RequireAnyClientCert), then this callback will be
    // considered but the verifiedChains argument will always be nil. When
    // ClientAuth is NoClientCert, this callback is not called on the server.
    // rawCerts may be empty on the server if ClientAuth is RequestClientCert or
    // VerifyClientCertIfGiven.
    //
    // This callback is not invoked on resumed connections, as certificates are
    // not re-verified on resumption.
    //
    // verifiedChains and its contents should not be modified.
    VerifyPeerCertificate func(rawCerts [][]byte, verifiedChains [][]*x509.Certificate) error // Go 1.8

    // VerifyConnection, if not nil, is called after normal certificate
    // verification and after VerifyPeerCertificate by either a TLS client
    // or server. If it returns a non-nil error, the handshake is aborted
    // and that error results.
    //
    // If normal verification fails then the handshake will abort before
    // considering this callback. This callback will run for all connections,
    // including resumptions, regardless of InsecureSkipVerify or ClientAuth
    // settings.
    VerifyConnection func(ConnectionState) error // Go 1.15

    // RootCAs defines the set of root certificate authorities
    // that clients use when verifying server certificates.
    // If RootCAs is nil, TLS uses the host's root CA set.
    RootCAs *x509.CertPool

    // NextProtos is a list of supported application level protocols, in
    // order of preference. If both peers support ALPN, the selected
    // protocol will be one from this list, and the connection will fail
    // if there is no mutually supported protocol. If NextProtos is empty
    // or the peer doesn't support ALPN, the connection will succeed and
    // ConnectionState.NegotiatedProtocol will be empty.
    NextProtos []string

    // ServerName is used to verify the hostname on the returned
    // certificates unless InsecureSkipVerify is given. It is also included
    // in the client's handshake to support virtual hosting unless it is
    // an IP address.
    ServerName string

    // ClientAuth determines the server's policy for
    // TLS Client Authentication. The default is NoClientCert.
    ClientAuth ClientAuthType

    // ClientCAs defines the set of root certificate authorities
    // that servers use if required to verify a client certificate
    // by the policy in ClientAuth.
    ClientCAs *x509.CertPool

    // InsecureSkipVerify controls whether a client verifies the server's
    // certificate chain and host name. If InsecureSkipVerify is true, crypto/tls
    // accepts any certificate presented by the server and any host name in that
    // certificate. In this mode, TLS is susceptible to machine-in-the-middle
    // attacks unless custom verification is used. This should be used only for
    // testing or in combination with VerifyConnection or VerifyPeerCertificate.
    InsecureSkipVerify bool

    // CipherSuites is a list of enabled TLS 1.0–1.2 cipher suites. The order of
    // the list is ignored. Note that TLS 1.3 ciphersuites are not configurable.
    //
    // If CipherSuites is nil, a safe default list is used. The default cipher
    // suites might change over time.
    CipherSuites []uint16

    // PreferServerCipherSuites is a legacy field and has no effect.
    //
    // It used to control whether the server would follow the client's or the
    // server's preference. Servers now select the best mutually supported
    // cipher suite based on logic that takes into account inferred client
    // hardware, server hardware, and security.
    //
    // Deprecated: PreferServerCipherSuites is ignored.
    PreferServerCipherSuites bool // Go 1.1

    // SessionTicketsDisabled may be set to true to disable session ticket and
    // PSK (resumption) support. Note that on clients, session ticket support is
    // also disabled if ClientSessionCache is nil.
    SessionTicketsDisabled bool // Go 1.1

    // SessionTicketKey is used by TLS servers to provide session resumption.
    // See RFC 5077 and the PSK mode of RFC 8446. If zero, it will be filled
    // with random data before the first server handshake.
    //
    // Deprecated: if this field is left at zero, session ticket keys will be
    // automatically rotated every day and dropped after seven days. For
    // customizing the rotation schedule or synchronizing servers that are
    // terminating connections for the same host, use SetSessionTicketKeys.
    SessionTicketKey [32]byte // Go 1.1

    // ClientSessionCache is a cache of ClientSessionState entries for TLS
    // session resumption. It is only used by clients.
    ClientSessionCache ClientSessionCache // Go 1.3

    // UnwrapSession is called on the server to turn a ticket/identity
    // previously produced by [WrapSession] into a usable session.
    //
    // UnwrapSession will usually either decrypt a session state in the ticket
    // (for example with [Config.EncryptTicket]), or use the ticket as a handle
    // to recover a previously stored state. It must use [ParseSessionState] to
    // deserialize the session state.
    //
    // If UnwrapSession returns an error, the connection is terminated. If it
    // returns (nil, nil), the session is ignored. crypto/tls may still choose
    // not to resume the returned session.
    UnwrapSession func(identity []byte, cs ConnectionState) (*SessionState, error) // Go 1.21

    // WrapSession is called on the server to produce a session ticket/identity.
    //
    // WrapSession must serialize the session state with [SessionState.Bytes].
    // It may then encrypt the serialized state (for example with
    // [Config.DecryptTicket]) and use it as the ticket, or store the state and
    // return a handle for it.
    //
    // If WrapSession returns an error, the connection is terminated.
    //
    // Warning: the return value will be exposed on the wire and to clients in
    // plaintext. The application is in charge of encrypting and authenticating
    // it (and rotating keys) or returning high-entropy identifiers. Failing to
    // do so correctly can compromise current, previous, and future connections
    // depending on the protocol version.
    WrapSession func(ConnectionState, *SessionState) ([]byte, error) // Go 1.21

    // MinVersion contains the minimum TLS version that is acceptable.
    //
    // By default, TLS 1.2 is currently used as the minimum when acting as a
    // client, and TLS 1.0 when acting as a server. TLS 1.0 is the minimum
    // supported by this package, both as a client and as a server.
    //
    // The client-side default can temporarily be reverted to TLS 1.0 by
    // including the value "x509sha1=1" in the GODEBUG environment variable.
    // Note that this option will be removed in Go 1.19 (but it will still be
    // possible to set this field to VersionTLS10 explicitly).
    MinVersion uint16 // Go 1.2

    // MaxVersion contains the maximum TLS version that is acceptable.
    //
    // By default, the maximum version supported by this package is used,
    // which is currently TLS 1.3.
    MaxVersion uint16 // Go 1.2

    // CurvePreferences contains the elliptic curves that will be used in
    // an ECDHE handshake, in preference order. If empty, the default will
    // be used. The client will use the first preference as the type for
    // its key share in TLS 1.3. This may change in the future.
    CurvePreferences []CurveID // Go 1.3

    // DynamicRecordSizingDisabled disables adaptive sizing of TLS records.
    // When true, the largest possible TLS record size is always used. When
    // false, the size of TLS records may be adjusted in an attempt to
    // improve latency.
    DynamicRecordSizingDisabled bool // Go 1.7

    // Renegotiation controls what types of renegotiation are supported.
    // The default, none, is correct for the vast majority of applications.
    Renegotiation RenegotiationSupport // Go 1.7

    // KeyLogWriter optionally specifies a destination for TLS master secrets
    // in NSS key log format that can be used to allow external programs
    // such as Wireshark to decrypt TLS connections.
    // See https://developer.mozilla.org/en-US/docs/Mozilla/Projects/NSS/Key_Log_Format.
    // Use of KeyLogWriter compromises security and should only be
    // used for debugging.
    KeyLogWriter io.Writer // Go 1.8
    // contains filtered or unexported fields
}
```

#### [Example (KeyLogWriter)]

Code:

```go
// Debugging TLS applications by decrypting a network traffic capture.

// WARNING: Use of KeyLogWriter compromises security and should only be
// used for debugging.

// Dummy test HTTP server for the example with insecure random so output is
// reproducible.
server := httptest.NewUnstartedServer(http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) {}))
server.TLS = &tls.Config{
    Rand: zeroSource{}, // for example only; don't do this.
}
server.StartTLS()
defer server.Close()

// Typically the log would go to an open file:
// w, err := os.OpenFile("tls-secrets.txt", os.O_WRONLY|os.O_CREATE|os.O_TRUNC, 0600)
w := os.Stdout

client := &http.Client{
    Transport: &http.Transport{
        TLSClientConfig: &tls.Config{
            KeyLogWriter: w,

            Rand:               zeroSource{}, // for reproducible output; don't do this.
            InsecureSkipVerify: true,         // test server certificate is not trusted.
        },
    },
}
resp, err := client.Get(server.URL)
if err != nil {
    log.Fatalf("Failed to get URL: %v", err)
}
resp.Body.Close()

// The resulting file can be used with Wireshark to decrypt the TLS
// connection by setting (Pre)-Master-Secret log filename in SSL Protocol
// preferences.
```

#### [Example (VerifyConnection)]

Code:

```go
// VerifyConnection can be used to replace and customize connection
// verification. This example shows a VerifyConnection implementation that
// will be approximately equivalent to what crypto/tls does normally to
// verify the peer's certificate.

// Client side configuration.
_ = &tls.Config{
    // Set InsecureSkipVerify to skip the default validation we are
    // replacing. This will not disable VerifyConnection.
    InsecureSkipVerify: true,
    VerifyConnection: func(cs tls.ConnectionState) error {
        opts := x509.VerifyOptions{
            DNSName:       cs.ServerName,
            Intermediates: x509.NewCertPool(),
        }
        for _, cert := range cs.PeerCertificates[1:] {
            opts.Intermediates.AddCert(cert)
        }
        _, err := cs.PeerCertificates[0].Verify(opts)
        return err
    },
}

// Server side configuration.
_ = &tls.Config{
    // Require client certificates (or VerifyConnection will run anyway and
    // panic accessing cs.PeerCertificates[0]) but don't verify them with the
    // default verifier. This will not disable VerifyConnection.
    ClientAuth: tls.RequireAnyClientCert,
    VerifyConnection: func(cs tls.ConnectionState) error {
        opts := x509.VerifyOptions{
            DNSName:       cs.ServerName,
            Intermediates: x509.NewCertPool(),
            KeyUsages:     []x509.ExtKeyUsage{x509.ExtKeyUsageClientAuth},
        }
        for _, cert := range cs.PeerCertificates[1:] {
            opts.Intermediates.AddCert(cert)
        }
        _, err := cs.PeerCertificates[0].Verify(opts)
        return err
    },
}

// Note that when certificates are not handled by the default verifier
// ConnectionState.VerifiedChains will be nil.
```

### func (\*Config) BuildNameToCertificate

```go
func (c *Config) BuildNameToCertificate()
```

BuildNameToCertificate parses c.Certificates and builds
c.NameToCertificate from the CommonName and SubjectAlternateName fields
of each of the leaf certificates.

Deprecated: NameToCertificate only allows associating a single
certificate with a given name. Leave that field nil to let the library
select the first compatible chain from Certificates.

### func (\*Config) Clone

```go
func (c *Config) Clone() *Config
```

Clone returns a shallow clone of c or nil if c is nil. It is safe to
clone a Config that is being used concurrently by a TLS client or
server.

### func (\*Config) DecryptTicket

```go
func (c *Config) DecryptTicket(identity []byte, cs ConnectionState) (*SessionState, error)
```

DecryptTicket decrypts a ticket encrypted by
[Config.EncryptTicket](#Config.EncryptTicket). It can be used as a
\[Config.UnwrapSession\] implementation.

If the ticket can\'t be decrypted or parsed, DecryptTicket returns (nil,
nil).

### func (\*Config) EncryptTicket

```go
func (c *Config) EncryptTicket(cs ConnectionState, ss *SessionState) ([]byte, error)
```

EncryptTicket encrypts a ticket with the Config\'s configured (or
default) session ticket keys. It can be used as a \[Config.WrapSession\]
implementation.

### func (\*Config) SetSessionTicketKeys

```go
func (c *Config) SetSessionTicketKeys(keys [][32]byte)
```

SetSessionTicketKeys updates the session ticket keys for a server.

The first key will be used when creating new tickets, while all keys can
be used for decrypting tickets. It is safe to call this function while
the server is running in order to rotate the session ticket keys. The
function will panic if keys is empty.

Calling this function will turn off automatic session ticket key
rotation.

If multiple servers are terminating connections for the same host they
should all have the same session ticket keys. If the session ticket keys
leaks, previously recorded and future TLS connections using those keys
might be compromised.

type Conn
---------

A Conn represents a secured connection. It implements the net.Conn
interface.

```go
type Conn struct {
    // contains filtered or unexported fields
}
```

### func Client

```go
func Client(conn net.Conn, config *Config) *Conn
```

Client returns a new TLS client side connection using conn as the
underlying transport. The config cannot be nil: users must set either
ServerName or InsecureSkipVerify in the config.

### func Dial

```go
func Dial(network, addr string, config *Config) (*Conn, error)
```

Dial connects to the given network address using net.Dial and then
initiates a TLS handshake, returning the resulting TLS connection. Dial
interprets a nil configuration as equivalent to the zero configuration;
see the documentation of Config for the defaults.

#### [Example]

Code:

```go
// Connecting with a custom root-certificate set.

const rootPEM = `
-- GlobalSign Root R2, valid until Dec 15, 2021
-----BEGIN CERTIFICATE-----
MIIDujCCAqKgAwIBAgILBAAAAAABD4Ym5g0wDQYJKoZIhvcNAQEFBQAwTDEgMB4G
A1UECxMXR2xvYmFsU2lnbiBSb290IENBIC0gUjIxEzARBgNVBAoTCkdsb2JhbFNp
Z24xEzARBgNVBAMTCkdsb2JhbFNpZ24wHhcNMDYxMjE1MDgwMDAwWhcNMjExMjE1
MDgwMDAwWjBMMSAwHgYDVQQLExdHbG9iYWxTaWduIFJvb3QgQ0EgLSBSMjETMBEG
A1UEChMKR2xvYmFsU2lnbjETMBEGA1UEAxMKR2xvYmFsU2lnbjCCASIwDQYJKoZI
hvcNAQEBBQADggEPADCCAQoCggEBAKbPJA6+Lm8omUVCxKs+IVSbC9N/hHD6ErPL
v4dfxn+G07IwXNb9rfF73OX4YJYJkhD10FPe+3t+c4isUoh7SqbKSaZeqKeMWhG8
eoLrvozps6yWJQeXSpkqBy+0Hne/ig+1AnwblrjFuTosvNYSuetZfeLQBoZfXklq
tTleiDTsvHgMCJiEbKjNS7SgfQx5TfC4LcshytVsW33hoCmEofnTlEnLJGKRILzd
C9XZzPnqJworc5HGnRusyMvo4KD0L5CLTfuwNhv2GXqF4G3yYROIXJ/gkwpRl4pa
zq+r1feqCapgvdzZX99yqWATXgAByUr6P6TqBwMhAo6CygPCm48CAwEAAaOBnDCB
mTAOBgNVHQ8BAf8EBAMCAQYwDwYDVR0TAQH/BAUwAwEB/zAdBgNVHQ4EFgQUm+IH
V2ccHsBqBt5ZtJot39wZhi4wNgYDVR0fBC8wLTAroCmgJ4YlaHR0cDovL2NybC5n
bG9iYWxzaWduLm5ldC9yb290LXIyLmNybDAfBgNVHSMEGDAWgBSb4gdXZxwewGoG
3lm0mi3f3BmGLjANBgkqhkiG9w0BAQUFAAOCAQEAmYFThxxol4aR7OBKuEQLq4Gs
J0/WwbgcQ3izDJr86iw8bmEbTUsp9Z8FHSbBuOmDAGJFtqkIk7mpM0sYmsL4h4hO
291xNBrBVNpGP+DTKqttVCL1OmLNIG+6KYnX3ZHu01yiPqFbQfXf5WRDLenVOavS
ot+3i9DAgBkcRcAtjOj4LaR0VknFBbVPFd5uRHg5h6h+u/N5GJG79G+dwfCMNYxd
AfvDbbnvRG15RjF+Cv6pgsH/76tuIMRQyV+dTZsXjAzlAcmgQWpzU/qlULRuJQ/7
TBj0/VLZjmmx6BEP3ojY+x1J96relc8geMJgEtslQIxq/H5COEBkEveegeGTLg==
-----END CERTIFICATE-----`

// First, create the set of root certificates. For this example we only
// have one. It's also possible to omit this in order to use the
// default root set of the current operating system.
roots := x509.NewCertPool()
ok := roots.AppendCertsFromPEM([]byte(rootPEM))
if !ok {
    panic("failed to parse root certificate")
}

conn, err := tls.Dial("tcp", "mail.google.com:443", &tls.Config{
    RootCAs: roots,
})
if err != nil {
    panic("failed to connect: " + err.Error())
}
conn.Close()
```

### func DialWithDialer

```go
func DialWithDialer(dialer *net.Dialer, network, addr string, config *Config) (*Conn, error)
```

DialWithDialer connects to the given network address using dialer.Dial
and then initiates a TLS handshake, returning the resulting TLS
connection. Any timeout or deadline given in the dialer apply to
connection and TLS handshake as a whole.

DialWithDialer interprets a nil configuration as equivalent to the zero
configuration; see the documentation of Config for the defaults.

DialWithDialer uses context.Background internally; to specify the
context, use Dialer.DialContext with NetDialer set to the desired
dialer.

### func Server

```go
func Server(conn net.Conn, config *Config) *Conn
```

Server returns a new TLS server side connection using conn as the
underlying transport. The configuration config must be non-nil and must
include at least one certificate or else set GetCertificate.

### func (\*Conn) Close

```go
func (c *Conn) Close() error
```

Close closes the connection.

### func (\*Conn) CloseWrite

```go
func (c *Conn) CloseWrite() error
```

CloseWrite shuts down the writing side of the connection. It should only
be called once the handshake has completed and does not call CloseWrite
on the underlying connection. Most callers should just use Close.

### func (\*Conn) ConnectionState

```go
func (c *Conn) ConnectionState() ConnectionState
```

ConnectionState returns basic TLS details about the connection.

### func (\*Conn) Handshake

```go
func (c *Conn) Handshake() error
```

Handshake runs the client or server handshake protocol if it has not yet
been run.

Most uses of this package need not call Handshake explicitly: the first
Read or Write will call it automatically.

For control over canceling or setting a timeout on a handshake, use
HandshakeContext or the Dialer\'s DialContext method instead.

In order to avoid denial of service attacks, the maximum RSA key size
allowed in certificates sent by either the TLS server or client is
limited to 8192 bits. This limit can be overridden by setting
tlsmaxrsasize in the GODEBUG environment variable (e.g.
GODEBUG=tlsmaxrsasize=4096).

### func (\*Conn) HandshakeContext

```go
func (c *Conn) HandshakeContext(ctx context.Context) error
```

HandshakeContext runs the client or server handshake protocol if it has
not yet been run.

The provided Context must be non-nil. If the context is canceled before
the handshake is complete, the handshake is interrupted and an error is
returned. Once the handshake has completed, cancellation of the context
will not affect the connection.

Most uses of this package need not call HandshakeContext explicitly: the
first Read or Write will call it automatically.

### func (\*Conn) LocalAddr

```go
func (c *Conn) LocalAddr() net.Addr
```

LocalAddr returns the local network address.

### func (\*Conn) NetConn

```go
func (c *Conn) NetConn() net.Conn
```

NetConn returns the underlying connection that is wrapped by c. Note
that writing to or reading from this connection directly will corrupt
the TLS session.

### func (\*Conn) OCSPResponse

```go
func (c *Conn) OCSPResponse() []byte
```

OCSPResponse returns the stapled OCSP response from the TLS server, if
any. (Only valid for client connections.)

### func (\*Conn) Read

```go
func (c *Conn) Read(b []byte) (int, error)
```

Read reads data from the connection.

As Read calls Handshake, in order to prevent indefinite blocking a
deadline must be set for both Read and Write before Read is called when
the handshake has not yet completed. See SetDeadline, SetReadDeadline,
and SetWriteDeadline.

### func (\*Conn) RemoteAddr

```go
func (c *Conn) RemoteAddr() net.Addr
```

RemoteAddr returns the remote network address.

### func (\*Conn) SetDeadline

```go
func (c *Conn) SetDeadline(t time.Time) error
```

SetDeadline sets the read and write deadlines associated with the
connection. A zero value for t means Read and Write will not time out.
After a Write has timed out, the TLS state is corrupt and all future
writes will return the same error.

### func (\*Conn) SetReadDeadline

```go
func (c *Conn) SetReadDeadline(t time.Time) error
```

SetReadDeadline sets the read deadline on the underlying connection. A
zero value for t means Read will not time out.

### func (\*Conn) SetWriteDeadline

```go
func (c *Conn) SetWriteDeadline(t time.Time) error
```

SetWriteDeadline sets the write deadline on the underlying connection. A
zero value for t means Write will not time out. After a Write has timed
out, the TLS state is corrupt and all future writes will return the same
error.

### func (\*Conn) VerifyHostname

```go
func (c *Conn) VerifyHostname(host string) error
```

VerifyHostname checks that the peer certificate chain is valid for
connecting to host. If so, it returns nil; if not, it returns an error
describing the problem.

### func (\*Conn) Write

```go
func (c *Conn) Write(b []byte) (int, error)
```

Write writes data to the connection.

As Write calls Handshake, in order to prevent indefinite blocking a
deadline must be set for both Read and Write before Write is called when
the handshake has not yet completed. See SetDeadline, SetReadDeadline,
and SetWriteDeadline.

type ConnectionState
--------------------

ConnectionState records basic TLS details about the connection.

```go
type ConnectionState struct {
    // Version is the TLS version used by the connection (e.g. VersionTLS12).
    Version uint16 // Go 1.3

    // HandshakeComplete is true if the handshake has concluded.
    HandshakeComplete bool

    // DidResume is true if this connection was successfully resumed from a
    // previous session with a session ticket or similar mechanism.
    DidResume bool // Go 1.1

    // CipherSuite is the cipher suite negotiated for the connection (e.g.
    // TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256, TLS_AES_128_GCM_SHA256).
    CipherSuite uint16

    // NegotiatedProtocol is the application protocol negotiated with ALPN.
    NegotiatedProtocol string

    // NegotiatedProtocolIsMutual used to indicate a mutual NPN negotiation.
    //
    // Deprecated: this value is always true.
    NegotiatedProtocolIsMutual bool

    // ServerName is the value of the Server Name Indication extension sent by
    // the client. It's available both on the server and on the client side.
    ServerName string

    // PeerCertificates are the parsed certificates sent by the peer, in the
    // order in which they were sent. The first element is the leaf certificate
    // that the connection is verified against.
    //
    // On the client side, it can't be empty. On the server side, it can be
    // empty if Config.ClientAuth is not RequireAnyClientCert or
    // RequireAndVerifyClientCert.
    //
    // PeerCertificates and its contents should not be modified.
    PeerCertificates []*x509.Certificate

    // VerifiedChains is a list of one or more chains where the first element is
    // PeerCertificates[0] and the last element is from Config.RootCAs (on the
    // client side) or Config.ClientCAs (on the server side).
    //
    // On the client side, it's set if Config.InsecureSkipVerify is false. On
    // the server side, it's set if Config.ClientAuth is VerifyClientCertIfGiven
    // (and the peer provided a certificate) or RequireAndVerifyClientCert.
    //
    // VerifiedChains and its contents should not be modified.
    VerifiedChains [][]*x509.Certificate

    // SignedCertificateTimestamps is a list of SCTs provided by the peer
    // through the TLS handshake for the leaf certificate, if any.
    SignedCertificateTimestamps [][]byte // Go 1.5

    // OCSPResponse is a stapled Online Certificate Status Protocol (OCSP)
    // response provided by the peer for the leaf certificate, if any.
    OCSPResponse []byte // Go 1.5

    // TLSUnique contains the "tls-unique" channel binding value (see RFC 5929,
    // Section 3). This value will be nil for TLS 1.3 connections and for
    // resumed connections that don't support Extended Master Secret (RFC 7627).
    TLSUnique []byte // Go 1.4
    // contains filtered or unexported fields
}
```

### func (\*ConnectionState) ExportKeyingMaterial

```go
func (cs *ConnectionState) ExportKeyingMaterial(label string, context []byte, length int) ([]byte, error)
```

ExportKeyingMaterial returns length bytes of exported key material in a
new slice as defined in RFC 5705. If context is nil, it is not used as
part of the seed. If the connection was set to allow renegotiation via
Config.Renegotiation, this function will return an error.

There are conditions in which the returned values might not be unique to
a connection. See the Security Considerations sections of RFC 5705 and
RFC 7627, and https://mitls.org/pages/attacks/3SHAKE#channelbindings>.

type CurveID
-------------------------------------------

CurveID is the type of a TLS identifier for an elliptic curve. See
https://www.iana.org/assignments/tls-parameters/tls-parameters.xml#tls-parameters-8>.

In TLS 1.3, this type is called NamedGroup, but at this time this
library only supports Elliptic Curve based groups. See RFC 8446, Section
4.2.7.

```go
type CurveID uint16
```

```go
const (
    CurveP256 CurveID = 23
    CurveP384 CurveID = 24
    CurveP521 CurveID = 25
    X25519    CurveID = 29
)
```

### func (CurveID) String

```go
func (i CurveID) String() string
```

type Dialer
--------------------------------------------

Dialer dials TLS connections given a configuration and a Dialer for the
underlying connection.

```go
type Dialer struct {
    // NetDialer is the optional dialer to use for the TLS connections'
    // underlying TCP connections.
    // A nil NetDialer is equivalent to the net.Dialer zero value.
    NetDialer *net.Dialer

    // Config is the TLS configuration to use for new connections.
    // A nil configuration is equivalent to the zero
    // configuration; see the documentation of Config for the
    // defaults.
    Config *Config
}
```

### func (\*Dialer) Dial

```go
func (d *Dialer) Dial(network, addr string) (net.Conn, error)
```

Dial connects to the given network address and initiates a TLS
handshake, returning the resulting TLS connection.

The returned Conn, if any, will always be of type \*Conn.

Dial uses context.Background internally; to specify the context, use
DialContext.

### func (\*Dialer) DialContext

```go
func (d *Dialer) DialContext(ctx context.Context, network, addr string) (net.Conn, error)
```

DialContext connects to the given network address and initiates a TLS
handshake, returning the resulting TLS connection.

The provided Context must be non-nil. If the context expires before the
connection is complete, an error is returned. Once successfully
connected, any expiration of the context will not affect the connection.

The returned Conn, if any, will always be of type \*Conn.

type QUICConfig
------------------------------------------------

A QUICConfig configures a QUICConn.

```go
type QUICConfig struct {
    TLSConfig *Config
}
```

type QUICConn
----------------------------------------------

A QUICConn represents a connection which uses a QUIC implementation as
the underlying transport as described in RFC 9001.

Methods of QUICConn are not safe for concurrent use.

```go
type QUICConn struct {
    // contains filtered or unexported fields
}
```

### func QUICClient

```go
func QUICClient(config *QUICConfig) *QUICConn
```

QUICClient returns a new TLS client side connection using QUICTransport
as the underlying transport. The config cannot be nil.

The config\'s MinVersion must be at least TLS 1.3.

### func QUICServer

```go
func QUICServer(config *QUICConfig) *QUICConn
```

QUICServer returns a new TLS server side connection using QUICTransport
as the underlying transport. The config cannot be nil.

The config\'s MinVersion must be at least TLS 1.3.

### func (\*QUICConn) Close

```go
func (q *QUICConn) Close() error
```

Close closes the connection and stops any in-progress handshake.

### func (\*QUICConn) ConnectionState

```go
func (q *QUICConn) ConnectionState() ConnectionState
```

ConnectionState returns basic TLS details about the connection.

### func (\*QUICConn) HandleData

```go
func (q *QUICConn) HandleData(level QUICEncryptionLevel, data []byte) error
```

HandleData handles handshake bytes received from the peer. It may
produce connection events, which may be read with NextEvent.

### func (\*QUICConn) NextEvent

```go
func (q *QUICConn) NextEvent() QUICEvent
```

NextEvent returns the next event occurring on the connection. It returns
an event with a Kind of QUICNoEvent when no events are available.

### func (\*QUICConn) SendSessionTicket

```go
func (q *QUICConn) SendSessionTicket(opts QUICSessionTicketOptions) error
```

SendSessionTicket sends a session ticket to the client. It produces
connection events, which may be read with NextEvent. Currently, it can
only be called once.

### func (\*QUICConn) SetTransportParameters

```go
func (q *QUICConn) SetTransportParameters(params []byte)
```

SetTransportParameters sets the transport parameters to send to the
peer.

Server connections may delay setting the transport parameters until
after receiving the client\'s transport parameters. See
QUICTransportParametersRequired.

### func (\*QUICConn) Start

```go
func (q *QUICConn) Start(ctx context.Context) error
```

Start starts the client or server handshake protocol. It may produce
connection events, which may be read with NextEvent.

Start must be called at most once.

type QUICEncryptionLevel
---------------------------------------------------------

QUICEncryptionLevel represents a QUIC encryption level used to transmit
handshake messages.

```go
type QUICEncryptionLevel int
```

### func (QUICEncryptionLevel) String

```go
func (l QUICEncryptionLevel) String() string
```

type QUICEvent
-----------------------------------------------

A QUICEvent is an event occurring on a QUIC connection.

The type of event is specified by the Kind field. The contents of the
other fields are kind-specific.

```go
type QUICEvent struct {
    Kind QUICEventKind

    // Set for QUICSetReadSecret, QUICSetWriteSecret, and QUICWriteData.
    Level QUICEncryptionLevel

    // Set for QUICTransportParameters, QUICSetReadSecret, QUICSetWriteSecret, and QUICWriteData.
    // The contents are owned by crypto/tls, and are valid until the next NextEvent call.
    Data []byte

    // Set for QUICSetReadSecret and QUICSetWriteSecret.
    Suite uint16
}
```

type QUICEventKind
---------------------------------------------------

A QUICEventKind is a type of operation on a QUIC connection.

```go
type QUICEventKind int
```

```go
const (
    // QUICNoEvent indicates that there are no events available.
    QUICNoEvent QUICEventKind = iota

    // QUICSetReadSecret and QUICSetWriteSecret provide the read and write
    // secrets for a given encryption level.
    // QUICEvent.Level, QUICEvent.Data, and QUICEvent.Suite are set.
    //
    // Secrets for the Initial encryption level are derived from the initial
    // destination connection ID, and are not provided by the QUICConn.
    QUICSetReadSecret
    QUICSetWriteSecret

    // QUICWriteData provides data to send to the peer in CRYPTO frames.
    // QUICEvent.Data is set.
    QUICWriteData

    // QUICTransportParameters provides the peer's QUIC transport parameters.
    // QUICEvent.Data is set.
    QUICTransportParameters

    // QUICTransportParametersRequired indicates that the caller must provide
    // QUIC transport parameters to send to the peer. The caller should set
    // the transport parameters with QUICConn.SetTransportParameters and call
    // QUICConn.NextEvent again.
    //
    // If transport parameters are set before calling QUICConn.Start, the
    // connection will never generate a QUICTransportParametersRequired event.
    QUICTransportParametersRequired

    // QUICRejectedEarlyData indicates that the server rejected 0-RTT data even
    // if we offered it. It's returned before QUICEncryptionLevelApplication
    // keys are returned.
    QUICRejectedEarlyData

    // QUICHandshakeDone indicates that the TLS handshake has completed.
    QUICHandshakeDone
)
```

type QUICSessionTicketOptions
--------------------------------------------------------------

```go
type QUICSessionTicketOptions struct {
    // EarlyData specifies whether the ticket may be used for 0-RTT.
    EarlyData bool
}
```

type RecordHeaderError
-----------------------------------------------------

RecordHeaderError is returned when a TLS record header is invalid.

```go
type RecordHeaderError struct {
    // Msg contains a human readable string that describes the error.
    Msg string
    // RecordHeader contains the five bytes of TLS record header that
    // triggered the error.
    RecordHeader [5]byte
    // Conn provides the underlying net.Conn in the case that a client
    // sent an initial handshake that didn't look like TLS.
    // It is nil if there's already been a handshake or a TLS alert has
    // been written to the connection.
    Conn net.Conn // Go 1.12
}
```

### func (RecordHeaderError) Error

```go
func (e RecordHeaderError) Error() string
```

type RenegotiationSupport
--------------------------------------------------------

RenegotiationSupport enumerates the different levels of support for TLS
renegotiation. TLS renegotiation is the act of performing subsequent
handshakes on a connection after the first. This significantly
complicates the state machine and has been the source of numerous,
subtle security issues. Initiating a renegotiation is not supported, but
support for accepting renegotiation requests may be enabled.

Even when enabled, the server may not change its identity between
handshakes (i.e. the leaf certificate must be the same). Additionally,
concurrent handshake and application data flow is not permitted so
renegotiation can only be used with protocols that synchronise with the
renegotiation, such as HTTPS.

Renegotiation is not defined in TLS 1.3.

```go
type RenegotiationSupport int
```

```go
const (
    // RenegotiateNever disables renegotiation.
    RenegotiateNever RenegotiationSupport = iota

    // RenegotiateOnceAsClient allows a remote server to request
    // renegotiation once per connection.
    RenegotiateOnceAsClient

    // RenegotiateFreelyAsClient allows a remote server to repeatedly
    // request renegotiation.
    RenegotiateFreelyAsClient
)
```

type SessionState
--------------------------------------------------

A SessionState is a resumable session.

```go
type SessionState struct {

    // Extra is ignored by crypto/tls, but is encoded by [SessionState.Bytes]
    // and parsed by [ParseSessionState].
    //
    // This allows [Config.UnwrapSession]/[Config.WrapSession] and
    // [ClientSessionCache] implementations to store and retrieve additional
    // data alongside this session.
    //
    // To allow different layers in a protocol stack to share this field,
    // applications must only append to it, not replace it, and must use entries
    // that can be recognized even if out of order (for example, by starting
    // with a id and version prefix).
    Extra [][]byte

    // EarlyData indicates whether the ticket can be used for 0-RTT in a QUIC
    // connection. The application may set this to false if it is true to
    // decline to offer 0-RTT even if supported.
    EarlyData bool
    // contains filtered or unexported fields
}
```

### func ParseSessionState

```go
func ParseSessionState(data []byte) (*SessionState, error)
```

ParseSessionState parses a [SessionState](#SessionState) encoded by
[SessionState.Bytes](#SessionState.Bytes).

### func (\*SessionState) Bytes

```go
func (s *SessionState) Bytes() ([]byte, error)
```

Bytes encodes the session, including any private fields, so that it can
be parsed by [ParseSessionState](#ParseSessionState). The encoding
contains secret values critical to the security of future and possibly
past sessions.

The specific encoding should be considered opaque and may change
incompatibly between Go versions.

type SignatureScheme
---------------------------------------------------

SignatureScheme identifies a signature algorithm supported by TLS. See
RFC 8446, Section 4.2.3.

```go
type SignatureScheme uint16
```

```go
const (
    // RSASSA-PKCS1-v1_5 algorithms.
    PKCS1WithSHA256 SignatureScheme = 0x0401
    PKCS1WithSHA384 SignatureScheme = 0x0501
    PKCS1WithSHA512 SignatureScheme = 0x0601

    // RSASSA-PSS algorithms with public key OID rsaEncryption.
    PSSWithSHA256 SignatureScheme = 0x0804
    PSSWithSHA384 SignatureScheme = 0x0805
    PSSWithSHA512 SignatureScheme = 0x0806

    // ECDSA algorithms. Only constrained to a specific curve in TLS 1.3.
    ECDSAWithP256AndSHA256 SignatureScheme = 0x0403
    ECDSAWithP384AndSHA384 SignatureScheme = 0x0503
    ECDSAWithP521AndSHA512 SignatureScheme = 0x0603

    // EdDSA algorithms.
    Ed25519 SignatureScheme = 0x0807

    // Legacy signature and hash algorithms for TLS 1.2.
    PKCS1WithSHA1 SignatureScheme = 0x0201
    ECDSAWithSHA1 SignatureScheme = 0x0203
)
```

### func (SignatureScheme) String

```go
func (i SignatureScheme) String() string
```

Bugs
----

-

    The crypto/tls package only implements some countermeasures against
    Lucky13 attacks on CBC-mode encryption, and only on SHA1 variants.
    See https://www.isg.rhul.ac.uk/tls/TLStiming.pdf> and
    https://www.imperialviolet.org/2013/02/04/luckythirteen.html>.

Subdirectories
--------------

Name

Synopsis

[..](../index)

[fipsonly](fipsonly/index)

Package fipsonly restricts all TLS configuration to FIPS-approved
settings.

© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/crypto/tls/>
