Command fipsonly
================

Package fipsonly restricts all TLS configuration to FIPS-approved
settings.

The effect is triggered by importing the package anywhere in a program,
as in:

```go
import _ "crypto/tls/fipsonly"
```

This package only exists when using Go compiled with
GOEXPERIMENT=boringcrypto.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/crypto/tls/fipsonly/>

