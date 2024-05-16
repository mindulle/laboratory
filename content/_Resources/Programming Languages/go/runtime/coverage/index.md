Package coverage
================

-   `import "runtime/coverage"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)

Overview 
--------

Index 
-----

-   [func ClearCounters() error](#ClearCounters)
-   [func WriteCounters(w io.Writer) error](#WriteCounters)
-   [func WriteCountersDir(dir string) error](#WriteCountersDir)
-   [func WriteMeta(w io.Writer) error](#WriteMeta)
-   [func WriteMetaDir(dir string) error](#WriteMetaDir)

### Package files

apis.go emit.go hooks.go testsupport.go

func ClearCounters 
---------------------------------------------------

```go
func ClearCounters() error
```

ClearCounters clears/resets all coverage counter variables in the
currently running program. It returns an error if the program in
question was not built with the \"-cover\" flag. Clearing of coverage
counters is also not supported for programs not using atomic counter
mode (see more detailed comments below for the rationale here).

func WriteCounters 
---------------------------------------------------

```go
func WriteCounters(w io.Writer) error
```

WriteCounters writes coverage counter-data content for the currently
running program to the writer \'w\'. An error will be returned if the
operation can\'t be completed successfully (for example, if the
currently running program was not built with \"-cover\", or if a write
fails). The counter data written will be a snapshot taken at the point
of the invocation.

func WriteCountersDir 
------------------------------------------------------

```go
func WriteCountersDir(dir string) error
```

WriteCountersDir writes a coverage counter-data file for the currently
running program to the directory specified in \'dir\'. An error will be
returned if the operation can\'t be completed successfully (for example,
if the currently running program was not built with \"-cover\", or if
the directory does not exist). The counter data written will be a
snapshot taken at the point of the call.

func WriteMeta 
-----------------------------------------------

```go
func WriteMeta(w io.Writer) error
```

WriteMeta writes the meta-data content (the payload that would normally
be emitted to a meta-data file) for the currently running program to the
writer \'w\'. An error will be returned if the operation can\'t be
completed successfully (for example, if the currently running program
was not built with \"-cover\", or if a write fails).

func WriteMetaDir 
--------------------------------------------------

```go
func WriteMetaDir(dir string) error
```

WriteMetaDir writes a coverage meta-data file for the currently running
program to the directory specified in \'dir\'. An error will be returned
if the operation can\'t be completed successfully (for example, if the
currently running program was not built with \"-cover\", or if the
directory does not exist).

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/runtime/coverage/>

