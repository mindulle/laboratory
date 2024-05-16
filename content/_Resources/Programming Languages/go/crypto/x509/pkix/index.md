Package pkix
============

-   `import "crypto/x509/pkix"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)

Overview 
--------

Package pkix contains shared, low level structures used for ASN.1
parsing and serialization of X.509 certificates, CRL and OCSP.

Index 
-----

-   [type AlgorithmIdentifier](#AlgorithmIdentifier)
-   [type AttributeTypeAndValue](#AttributeTypeAndValue)
-   [type AttributeTypeAndValueSET](#AttributeTypeAndValueSET)
-   [type CertificateList](#CertificateList)
-   [func (certList \*CertificateList) HasExpired(now time.Time)
    bool](#CertificateList.HasExpired)
-   [type Extension](#Extension)
-   [type Name](#Name)
-   [func (n \*Name) FillFromRDNSequence(rdns
    \*RDNSequence)](#Name.FillFromRDNSequence)
-   [func (n Name) String() string](#Name.String)
-   [func (n Name) ToRDNSequence() (ret
    RDNSequence)](#Name.ToRDNSequence)
-   [type RDNSequence](#RDNSequence)
-   [func (r RDNSequence) String() string](#RDNSequence.String)
-   [type RelativeDistinguishedNameSET](#RelativeDistinguishedNameSET)
-   [type RevokedCertificate](#RevokedCertificate)
-   [type TBSCertificateList](#TBSCertificateList)

### Package files

pkix.go

type AlgorithmIdentifier 
------------------------

AlgorithmIdentifier represents the ASN.1 structure of the same name. See
RFC 5280, section 4.1.1.2.

```go
type AlgorithmIdentifier struct {
    Algorithm  asn1.ObjectIdentifier
    Parameters asn1.RawValue `asn1:"optional"`
}
```

type AttributeTypeAndValue 
--------------------------

AttributeTypeAndValue mirrors the ASN.1 structure of the same name in
RFC 5280, Section 4.1.2.4.

```go
type AttributeTypeAndValue struct {
    Type  asn1.ObjectIdentifier
    Value any
}
```

type AttributeTypeAndValueSET 
------------------------------------------------------------

AttributeTypeAndValueSET represents a set of ASN.1 sequences of
AttributeTypeAndValue sequences from RFC 2986 (PKCS \#10).

```go
type AttributeTypeAndValueSET struct {
    Type  asn1.ObjectIdentifier
    Value [][]AttributeTypeAndValue `asn1:"set"`
}
```

type CertificateList 
--------------------

CertificateList represents the ASN.1 structure of the same name. See RFC
5280, section 5.1. Use Certificate.CheckCRLSignature to verify the
signature.

Deprecated: x509.RevocationList should be used instead.

```go
type CertificateList struct {
    TBSCertList        TBSCertificateList
    SignatureAlgorithm AlgorithmIdentifier
    SignatureValue     asn1.BitString
}
```

### func (\*CertificateList) HasExpired 

```go
func (certList *CertificateList) HasExpired(now time.Time) bool
```

HasExpired reports whether certList should have been updated by now.

type Extension 
--------------

Extension represents the ASN.1 structure of the same name. See RFC 5280,
section 4.2.

```go
type Extension struct {
    Id       asn1.ObjectIdentifier
    Critical bool `asn1:"optional"`
    Value    []byte
}
```

type Name 
---------

Name represents an X.509 distinguished name. This only includes the
common elements of a DN. Note that Name is only an approximation of the
X.509 structure. If an accurate representation is needed, asn1.Unmarshal
the raw subject or issuer as an RDNSequence.

```go
type Name struct {
    Country, Organization, OrganizationalUnit []string
    Locality, Province                        []string
    StreetAddress, PostalCode                 []string
    SerialNumber, CommonName                  string

    // Names contains all parsed attributes. When parsing distinguished names,
    // this can be used to extract non-standard attributes that are not parsed
    // by this package. When marshaling to RDNSequences, the Names field is
    // ignored, see ExtraNames.
    Names []AttributeTypeAndValue

    // ExtraNames contains attributes to be copied, raw, into any marshaled
    // distinguished names. Values override any attributes with the same OID.
    // The ExtraNames field is not populated when parsing, see Names.
    ExtraNames []AttributeTypeAndValue // Go 1.5
}
```

### func (\*Name) FillFromRDNSequence 

```go
func (n *Name) FillFromRDNSequence(rdns *RDNSequence)
```

FillFromRDNSequence populates n from the provided RDNSequence.
Multi-entry RDNs are flattened, all entries are added to the relevant n
fields, and the grouping is not preserved.

### func (Name) String 

```go
func (n Name) String() string
```

String returns the string form of n, roughly following the RFC 2253
Distinguished Names syntax.

### func (Name) ToRDNSequence 

```go
func (n Name) ToRDNSequence() (ret RDNSequence)
```

ToRDNSequence converts n into a single RDNSequence. The following
attributes are encoded as multi-value RDNs:

-   Country
-   Organization
-   OrganizationalUnit
-   Locality
-   Province
-   StreetAddress
-   PostalCode

Each ExtraNames entry is encoded as an individual RDN.

type RDNSequence 
----------------

```go
type RDNSequence []RelativeDistinguishedNameSET
```

### func (RDNSequence) String 

```go
func (r RDNSequence) String() string
```

String returns a string representation of the sequence r, roughly
following the RFC 2253 Distinguished Names syntax.

type RelativeDistinguishedNameSET 
---------------------------------

```go
type RelativeDistinguishedNameSET []AttributeTypeAndValue
```

type RevokedCertificate 
-----------------------

RevokedCertificate represents the ASN.1 structure of the same name. See
RFC 5280, section 5.1.

```go
type RevokedCertificate struct {
    SerialNumber   *big.Int
    RevocationTime time.Time
    Extensions     []Extension `asn1:"optional"`
}
```

type TBSCertificateList 
-----------------------

TBSCertificateList represents the ASN.1 structure of the same name. See
RFC 5280, section 5.1.

Deprecated: x509.RevocationList should be used instead.

```go
type TBSCertificateList struct {
    Raw                 asn1.RawContent
    Version             int `asn1:"optional,default:0"`
    Signature           AlgorithmIdentifier
    Issuer              RDNSequence
    ThisUpdate          time.Time
    NextUpdate          time.Time            `asn1:"optional"`
    RevokedCertificates []RevokedCertificate `asn1:"optional"`
    Extensions          []Extension          `asn1:"tag:0,optional,explicit"`
}
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/crypto/x509/pkix/>

