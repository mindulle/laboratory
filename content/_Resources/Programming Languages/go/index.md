Go Programming Language
=======================

-   [Sub-repositories](#subrepo)
-   [Community](#community)

Standard library 
----------------

 
  Name
  -----------------------------------------------
  [tar](archive/tar/index)
  [zip](archive/zip/index)
  [arena](arena/index)
  [bufio](bufio/index)
  [builtin](builtin/index)
  [bytes](bytes/index)
  [cmp](cmp/index)
  [compress](compress/index)
  [bzip2](compress/bzip2/index)
  [flate](compress/flate/index)
  [gzip](compress/gzip/index)
  [lzw](compress/lzw/index)
  [zlib](compress/zlib/index)
  [container](container/index)
  [heap](container/heap/index)
  [list](container/list/index)
  [ring](container/ring/index)
  [context](context/index)
  [crypto](crypto/index)
  [aes](crypto/aes/index)
  [boring](crypto/boring/index)
  [cipher](crypto/cipher/index)
  [des](crypto/des/index)
  [dsa](crypto/dsa/index)
  [ecdh](crypto/ecdh/index)
  [ecdsa](crypto/ecdsa/index)
  [ed25519](crypto/ed25519/index)
  [elliptic](crypto/elliptic/index)
  [hmac](crypto/hmac/index)
  [md5](crypto/md5/index)
  [rand](crypto/rand/index)
  [rc4](crypto/rc4/index)
  [rsa](crypto/rsa/index)
  [sha1](crypto/sha1/index)
  [sha256](crypto/sha256/index)
  [sha512](crypto/sha512/index)
  [subtle](crypto/subtle/index)
  [tls](crypto/tls/index)
  [fipsonly](crypto/tls/fipsonly/index)
  [x509](crypto/x509/index)
  [pkix](crypto/x509/pkix/index)
  [database](database/index)
  [sql](database/sql/index)
  [driver](database/sql/driver/index)
  [debug](debug/index)
  [buildinfo](debug/buildinfo/index)
  [dwarf](debug/dwarf/index)
  [elf](debug/elf/index)
  [gosym](debug/gosym/index)
  [macho](debug/macho/index)
  [pe](debug/pe/index)
  [plan9obj](debug/plan9obj/index)
  [embed](embed/index)
  [encoding](encoding/index)
  [ascii85](encoding/ascii85/index)
  [asn1](encoding/asn1/index)
  [base32](encoding/base32/index)
  [base64](encoding/base64/index)
  [binary](encoding/binary/index)
  [csv](encoding/csv/index)
  [gob](encoding/gob/index)
  [hex](encoding/hex/index)
  [json](encoding/json/index)
  [pem](encoding/pem/index)
  [xml](encoding/xml/index)
  [errors](errors/index)
  [expvar](expvar/index)
  [flag](flag/index)
  [fmt](fmt/index)
  [go](go/index)
  [ast](go/ast/index)
  [build](go/build/index)
  [constraint](go/build/constraint/index)
  [constant](go/constant/index)
  [doc](go/doc/index)
  [comment](go/doc/comment/index)
  [format](go/format/index)
  [importer](go/importer/index)
  [parser](go/parser/index)
  [printer](go/printer/index)
  [scanner](go/scanner/index)
  [token](go/token/index)
  [types](go/types/index)
  [hash](hash/index)
  [adler32](hash/adler32/index)
  [crc32](hash/crc32/index)
  [crc64](hash/crc64/index)
  [fnv](hash/fnv/index)
  [maphash](hash/maphash/index)
  [html](html/index)
  [template](html/template/index)
  [image](image/index)
  [color](image/color/index)
  [palette](image/color/palette/index)
  [draw](image/draw/index)
  [gif](image/gif/index)
  [jpeg](image/jpeg/index)
  [png](image/png/index)
  [index](index/index)
  [suffixarray](index/suffixarray/index)
  [io](io/index)
  [fs](io/fs/index)
  [ioutil](io/ioutil/index)
  [log](log/index)
  [slog](log/slog/index)
  [syslog](log/syslog/index)
  [maps](maps/index)
  [math](math/index)
  [big](math/big/index)
  [bits](math/bits/index)
  [cmplx](math/cmplx/index)
  [rand](math/rand/index)
  [mime](mime/index)
  [multipart](mime/multipart/index)
  [quotedprintable](mime/quotedprintable/index)
  [net](net/index)
  [http](net/http/index)
  [cgi](net/http/cgi/index)
  [cookiejar](net/http/cookiejar/index)
  [fcgi](net/http/fcgi/index)
  [httptest](net/http/httptest/index)
  [httptrace](net/http/httptrace/index)
  [httputil](net/http/httputil/index)
  [pprof](net/http/pprof/index)
  [mail](net/mail/index)
  [netip](net/netip/index)
  [rpc](net/rpc/index)
  [jsonrpc](net/rpc/jsonrpc/index)
  [smtp](net/smtp/index)
  [textproto](net/textproto/index)
  [url](net/url/index)
  [os](os/index)
  [exec](os/exec/index)
  [signal](os/signal/index)
  [user](os/user/index)
  [path](path/index)
  [filepath](path/filepath/index)
  [plugin](plugin/index)
  [reflect](reflect/index)
  [regexp](regexp/index)
  [syntax](regexp/syntax/index)
  [runtime](runtime/index)
  [asan](runtime/asan/index)
  [cgo](runtime/cgo/index)
  [coverage](runtime/coverage/index)
  [debug](runtime/debug/index)
  [metrics](runtime/metrics/index)
  msan
  [pprof](runtime/pprof/index)
  [race](runtime/race/index)
  [trace](runtime/trace/index)
  [slices](slices/index)
  [sort](sort/index)
  [strconv](strconv/index)
  [strings](strings/index)
  [sync](sync/index)
  [atomic](sync/atomic/index)
  [syscall](syscall/index)
  [js](syscall/js/index)
  [testing](testing/index)
  [fstest](testing/fstest/index)
  [iotest](testing/iotest/index)
  [quick](testing/quick/index)
  [slogtest](testing/slogtest/index)
  [text](text/index)
  [scanner](text/scanner/index)
  [tabwriter](text/tabwriter/index)
  [template](text/template/index)
  [parse](text/template/parse/index)
  [time](time/index)
  [tzdata](time/tzdata/index)
  [unicode](unicode/index)
  [utf16](unicode/utf16/index)
  [utf8](unicode/utf8/index)
  [unsafe](unsafe/index)


Other packages 
--------------

### Sub-repositories 

These packages are part of the Go Project but outside the main Go tree.
They are developed under looser [compatibility
requirements](https://golang.org/doc/go1compat) than the Go core.
Install them with \"go get\".

-   [benchmarks](http://pkg.go.dev:6060/golang.org/x/benchmarks) ---
    benchmarks to measure Go as it is developed.
-   [blog](http://pkg.go.dev:6060/golang.org/x/blog) ---
    [blog.golang.org](http://blog.golang.org:6060)\'s implementation.
-   [build](http://pkg.go.dev:6060/golang.org/x/build) ---
    [build.golang.org](http://build.golang.org:6060)\'s implementation.
-   [crypto](http://pkg.go.dev:6060/golang.org/x/crypto) --- additional
    cryptography packages.
-   [debug](http://pkg.go.dev:6060/golang.org/x/debug) --- an
    experimental debugger for Go.
-   [image](http://pkg.go.dev:6060/golang.org/x/image) --- additional
    imaging packages.
-   [mobile](http://pkg.go.dev:6060/golang.org/x/mobile) ---
    experimental support for Go on mobile platforms.
-   [net](http://pkg.go.dev:6060/golang.org/x/net) --- additional
    networking packages.
-   [perf](http://pkg.go.dev:6060/golang.org/x/perf) --- packages and
    tools for performance measurement, storage, and analysis.
-   [pkgsite](http://pkg.go.dev:6060/golang.org/x/pkgsite) --- home of
    the pkg.go.dev website.
-   [review](http://pkg.go.dev:6060/golang.org/x/review) --- a tool for
    working with Gerrit code reviews.
-   [sync](http://pkg.go.dev:6060/golang.org/x/sync) --- additional
    concurrency primitives.
-   [sys](http://pkg.go.dev:6060/golang.org/x/sys) --- packages for
    making system calls.
-   [text](http://pkg.go.dev:6060/golang.org/x/text) --- packages for
    working with text.
-   [time](http://pkg.go.dev:6060/golang.org/x/time) --- additional time
    packages.
-   [tools](http://pkg.go.dev:6060/golang.org/x/tools) --- godoc,
    goimports, gorename, and other tools.
-   [tour](http://pkg.go.dev:6060/golang.org/x/tour) ---
    [tour.golang.org](http://tour.golang.org:6060)\'s implementation.
-   [exp](http://pkg.go.dev:6060/golang.org/x/exp) --- experimental and
    deprecated packages (handle with care; may change without warning).

### Community

These services can help you find Open Source packages provided by the
community.

-   [Pkg.go.dev](http://pkg.go.dev:6060) - the Go package discovery
    site.
-   Projects at the Go Wiki - a curated list of Go projects.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg//>

