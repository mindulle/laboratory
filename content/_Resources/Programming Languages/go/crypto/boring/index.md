Command boring
==============

Package boring exposes functions that are only available when building
with Go+BoringCrypto. This package is available on all targets as long
as the Go+BoringCrypto toolchain is used. Use the Enabled function to
determine whether the BoringCrypto core is actually in use.

Any time the Go+BoringCrypto toolchain is used, the \"boringcrypto\"
build tag is satisfied, so that applications can tag files that use this
package.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/crypto/boring/>

