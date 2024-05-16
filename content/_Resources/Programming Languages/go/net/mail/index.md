Package mail
============

-   `import "net/mail"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package mail implements parsing of mail messages.

For the most part, this package follows the syntax as specified by RFC
5322 and extended by RFC 6532. Notable divergences:

-   Obsolete address formats are not parsed, including addresses with
    embedded route information.
-   The full range of spacing (the CFWS syntax element) is not
    supported, such as breaking addresses across lines.
-   No unicode normalization is performed.
-   The special characters ()\[\]:;@\\, are allowed to appear unquoted
    in names.
-   A leading From line is permitted, as in mbox format (RFC 4155).

Index 
-----

-   [Variables](#pkg-variables)
-   [func ParseDate(date string) (time.Time, error)](#ParseDate)
-   [type Address](#Address)
-   [func ParseAddress(address string) (\*Address,
    error)](#ParseAddress)
-   [func ParseAddressList(list string) (\[\]\*Address,
    error)](#ParseAddressList)
-   [func (a \*Address) String() string](#Address.String)
-   [type AddressParser](#AddressParser)
-   [func (p \*AddressParser) Parse(address string) (\*Address,
    error)](#AddressParser.Parse)
-   [func (p \*AddressParser) ParseList(list string) (\[\]\*Address,
    error)](#AddressParser.ParseList)
-   [type Header](#Header)
-   [func (h Header) AddressList(key string) (\[\]\*Address,
    error)](#Header.AddressList)
-   [func (h Header) Date() (time.Time, error)](#Header.Date)
-   [func (h Header) Get(key string) string](#Header.Get)
-   [type Message](#Message)
-   [func ReadMessage(r io.Reader) (msg \*Message, err
    error)](#ReadMessage)

 
### Examples

[ParseAddress](#example_ParseAddress)

[ParseAddressList](#example_ParseAddressList)

[ReadMessage](#example_ReadMessage)


### Package files

message.go

Variables 
---------

```go
var ErrHeaderNotPresent = errors.New("mail: header not in message")
```

func ParseDate 
---------------------------------------------

```go
func ParseDate(date string) (time.Time, error)
```

ParseDate parses an RFC 5322 date string.

type Address 
------------

Address represents a single mail address. An address such as \"Barry
Gibbs \<bg\@example.com\>\" is represented as Address\{Name: \"Barry
Gibbs\", Address: \"bg\@example.com\"\}.

```go
type Address struct {
    Name    string // Proper name; may be empty.
    Address string // user@domain
}
```

### func ParseAddress 1.1

```go
func ParseAddress(address string) (*Address, error)
```

ParseAddress parses a single RFC 5322 address, e.g. \"Barry Gibbs
\<bg\@example.com\>\"

#### [Example]

Code:

```go
e, err := mail.ParseAddress("Alice <alice@example.com>")
if err != nil {
    log.Fatal(err)
}

fmt.Println(e.Name, e.Address)
```

Output:

```go
Alice alice@example.com
```

### func ParseAddressList 

```go
func ParseAddressList(list string) ([]*Address, error)
```

ParseAddressList parses the given string as a list of addresses.

#### [Example]

Code:

```go
const list = "Alice <alice@example.com>, Bob <bob@example.com>, Eve <eve@example.com>"
emails, err := mail.ParseAddressList(list)
if err != nil {
    log.Fatal(err)
}

for _, v := range emails {
    fmt.Println(v.Name, v.Address)
}
```

Output:

```go
Alice alice@example.com
Bob bob@example.com
Eve eve@example.com
```

### func (\*Address) String 

```go
func (a *Address) String() string
```

String formats the address as a valid RFC 5322 address. If the
address\'s name contains non-ASCII characters the name will be rendered
according to RFC 2047.

type AddressParser 
-------------------------------------------------

An AddressParser is an RFC 5322 address parser.

```go
type AddressParser struct {
    // WordDecoder optionally specifies a decoder for RFC 2047 encoded-words.
    WordDecoder *mime.WordDecoder
}
```

### func (\*AddressParser) Parse 

```go
func (p *AddressParser) Parse(address string) (*Address, error)
```

Parse parses a single RFC 5322 address of the form \"Gogh Fir
\<gf\@example.com\>\" or \"foo\@example.com\".

### func (\*AddressParser) ParseList 

```go
func (p *AddressParser) ParseList(list string) ([]*Address, error)
```

ParseList parses the given string as a list of comma-separated addresses
of the form \"Gogh Fir \<gf\@example.com\>\" or \"foo\@example.com\".

type Header 
-----------

A Header represents the key-value pairs in a mail message header.

```go
type Header map[string][]string
```

### func (Header) AddressList 

```go
func (h Header) AddressList(key string) ([]*Address, error)
```

AddressList parses the named header field as a list of addresses.

### func (Header) Date 

```go
func (h Header) Date() (time.Time, error)
```

Date parses the Date header field.

### func (Header) Get 

```go
func (h Header) Get(key string) string
```

Get gets the first value associated with the given key. It is case
insensitive; CanonicalMIMEHeaderKey is used to canonicalize the provided
key. If there are no values associated with the key, Get returns \"\".
To access multiple values of a key, or to use non-canonical keys, access
the map directly.

type Message 
------------

A Message represents a parsed mail message.

```go
type Message struct {
    Header Header
    Body   io.Reader
}
```

### func ReadMessage 

```go
func ReadMessage(r io.Reader) (msg *Message, err error)
```

ReadMessage reads a message from r. The headers are parsed, and the body
of the message will be available for reading from msg.Body.

#### [Example]

Code:

```go
msg := `Date: Mon, 23 Jun 2015 11:40:36 -0400
From: Gopher <from@example.com>
To: Another Gopher <to@example.com>
Subject: Gophers at Gophercon

Message body
`

r := strings.NewReader(msg)
m, err := mail.ReadMessage(r)
if err != nil {
    log.Fatal(err)
}

header := m.Header
fmt.Println("Date:", header.Get("Date"))
fmt.Println("From:", header.Get("From"))
fmt.Println("To:", header.Get("To"))
fmt.Println("Subject:", header.Get("Subject"))

body, err := io.ReadAll(m.Body)
if err != nil {
    log.Fatal(err)
}
fmt.Printf("%s", body)
```

Output:

```go
Date: Mon, 23 Jun 2015 11:40:36 -0400
From: Gopher <from@example.com>
To: Another Gopher <to@example.com>
Subject: Gophers at Gophercon
Message body
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/net/mail/>

