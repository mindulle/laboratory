Package os
==========

-   `import "os"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)
-   [Subdirectories](#pkg-subdirectories)

Overview 
--------

Package os provides a platform-independent interface to operating system
functionality. The design is Unix-like, although the error handling is
Go-like; failing calls return values of type error rather than error
numbers. Often, more information is available within the error. For
example, if a call that takes a file name fails, such as Open or Stat,
the error will include the failing file name when printed and will be of
type \*PathError, which may be unpacked for more information.

The os interface is intended to be uniform across all operating systems.
Features not generally available appear in the system-specific package
syscall.

Here is a simple example, opening a file and reading some of it.

```go
file, err := os.Open("file.go") // For read access.
if err != nil {
    log.Fatal(err)
}
```

If the open fails, the error string will be self-explanatory, like

```go
open file.go: no such file or directory
```

The file\'s data can then be read into a slice of bytes. Read and Write
take their byte counts from the length of the argument slice.

```go
data := make([]byte, 100)
count, err := file.Read(data)
if err != nil {
    log.Fatal(err)
}
fmt.Printf("read %d bytes: %q\n", count, data[:count])
```

Note: The maximum number of concurrent operations on a File may be
limited by the OS or the system. The number should be high, but
exceeding it may degrade performance or cause other issues.

Index 
-----

-   [Constants](#pkg-constants)
-   [Variables](#pkg-variables)
-   [func Chdir(dir string) error](#Chdir)
-   [func Chmod(name string, mode FileMode) error](#Chmod)
-   [func Chown(name string, uid, gid int) error](#Chown)
-   [func Chtimes(name string, atime time.Time, mtime time.Time)
    error](#Chtimes)
-   [func Clearenv()](#Clearenv)
-   [func DirFS(dir string) fs.FS](#DirFS)
-   [func Environ() \[\]string](#Environ)
-   [func Executable() (string, error)](#Executable)
-   [func Exit(code int)](#Exit)
-   [func Expand(s string, mapping func(string) string) string](#Expand)
-   [func ExpandEnv(s string) string](#ExpandEnv)
-   [func Getegid() int](#Getegid)
-   [func Getenv(key string) string](#Getenv)
-   [func Geteuid() int](#Geteuid)
-   [func Getgid() int](#Getgid)
-   [func Getgroups() (\[\]int, error)](#Getgroups)
-   [func Getpagesize() int](#Getpagesize)
-   [func Getpid() int](#Getpid)
-   [func Getppid() int](#Getppid)
-   [func Getuid() int](#Getuid)
-   [func Getwd() (dir string, err error)](#Getwd)
-   [func Hostname() (name string, err error)](#Hostname)
-   [func IsExist(err error) bool](#IsExist)
-   [func IsNotExist(err error) bool](#IsNotExist)
-   [func IsPathSeparator(c uint8) bool](#IsPathSeparator)
-   [func IsPermission(err error) bool](#IsPermission)
-   [func IsTimeout(err error) bool](#IsTimeout)
-   [func Lchown(name string, uid, gid int) error](#Lchown)
-   [func Link(oldname, newname string) error](#Link)
-   [func LookupEnv(key string) (string, bool)](#LookupEnv)
-   [func Mkdir(name string, perm FileMode) error](#Mkdir)
-   [func MkdirAll(path string, perm FileMode) error](#MkdirAll)
-   [func MkdirTemp(dir, pattern string) (string, error)](#MkdirTemp)
-   [func NewSyscallError(syscall string, err error)
    error](#NewSyscallError)
-   [func Pipe() (r \*File, w \*File, err error)](#Pipe)
-   [func ReadFile(name string) (\[\]byte, error)](#ReadFile)
-   [func Readlink(name string) (string, error)](#Readlink)
-   [func Remove(name string) error](#Remove)
-   [func RemoveAll(path string) error](#RemoveAll)
-   [func Rename(oldpath, newpath string) error](#Rename)
-   [func SameFile(fi1, fi2 FileInfo) bool](#SameFile)
-   [func Setenv(key, value string) error](#Setenv)
-   [func Symlink(oldname, newname string) error](#Symlink)
-   [func TempDir() string](#TempDir)
-   [func Truncate(name string, size int64) error](#Truncate)
-   [func Unsetenv(key string) error](#Unsetenv)
-   [func UserCacheDir() (string, error)](#UserCacheDir)
-   [func UserConfigDir() (string, error)](#UserConfigDir)
-   [func UserHomeDir() (string, error)](#UserHomeDir)
-   [func WriteFile(name string, data \[\]byte, perm FileMode)
    error](#WriteFile)
-   [type DirEntry](#DirEntry)
-   [func ReadDir(name string) (\[\]DirEntry, error)](#ReadDir)
-   [type File](#File)
-   [func Create(name string) (\*File, error)](#Create)
-   [func CreateTemp(dir, pattern string) (\*File, error)](#CreateTemp)
-   [func NewFile(fd uintptr, name string) \*File](#NewFile)
-   [func Open(name string) (\*File, error)](#Open)
-   [func OpenFile(name string, flag int, perm FileMode) (\*File,
    error)](#OpenFile)
-   [func (f \*File) Chdir() error](#File.Chdir)
-   [func (f \*File) Chmod(mode FileMode) error](#File.Chmod)
-   [func (f \*File) Chown(uid, gid int) error](#File.Chown)
-   [func (f \*File) Close() error](#File.Close)
-   [func (f \*File) Fd() uintptr](#File.Fd)
-   [func (f \*File) Name() string](#File.Name)
-   [func (f \*File) Read(b \[\]byte) (n int, err error)](#File.Read)
-   [func (f \*File) ReadAt(b \[\]byte, off int64) (n int, err
    error)](#File.ReadAt)
-   [func (f \*File) ReadDir(n int) (\[\]DirEntry,
    error)](#File.ReadDir)
-   [func (f \*File) ReadFrom(r io.Reader) (n int64, err
    error)](#File.ReadFrom)
-   [func (f \*File) Readdir(n int) (\[\]FileInfo,
    error)](#File.Readdir)
-   [func (f \*File) Readdirnames(n int) (names \[\]string, err
    error)](#File.Readdirnames)
-   [func (f \*File) Seek(offset int64, whence int) (ret int64, err
    error)](#File.Seek)
-   [func (f \*File) SetDeadline(t time.Time) error](#File.SetDeadline)
-   [func (f \*File) SetReadDeadline(t time.Time)
    error](#File.SetReadDeadline)
-   [func (f \*File) SetWriteDeadline(t time.Time)
    error](#File.SetWriteDeadline)
-   [func (f \*File) Stat() (FileInfo, error)](#File.Stat)
-   [func (f \*File) Sync() error](#File.Sync)
-   [func (f \*File) SyscallConn() (syscall.RawConn,
    error)](#File.SyscallConn)
-   [func (f \*File) Truncate(size int64) error](#File.Truncate)
-   [func (f \*File) Write(b \[\]byte) (n int, err error)](#File.Write)
-   [func (f \*File) WriteAt(b \[\]byte, off int64) (n int, err
    error)](#File.WriteAt)
-   [func (f \*File) WriteString(s string) (n int, err
    error)](#File.WriteString)
-   [type FileInfo](#FileInfo)
-   [func Lstat(name string) (FileInfo, error)](#Lstat)
-   [func Stat(name string) (FileInfo, error)](#Stat)
-   [type FileMode](#FileMode)
-   [type LinkError](#LinkError)
-   [func (e \*LinkError) Error() string](#LinkError.Error)
-   [func (e \*LinkError) Unwrap() error](#LinkError.Unwrap)
-   [type PathError](#PathError)
-   [type ProcAttr](#ProcAttr)
-   [type Process](#Process)
-   [func FindProcess(pid int) (\*Process, error)](#FindProcess)
-   [func StartProcess(name string, argv \[\]string, attr \*ProcAttr)
    (\*Process, error)](#StartProcess)
-   [func (p \*Process) Kill() error](#Process.Kill)
-   [func (p \*Process) Release() error](#Process.Release)
-   [func (p \*Process) Signal(sig Signal) error](#Process.Signal)
-   [func (p \*Process) Wait() (\*ProcessState, error)](#Process.Wait)
-   [type ProcessState](#ProcessState)
-   [func (p \*ProcessState) ExitCode() int](#ProcessState.ExitCode)
-   [func (p \*ProcessState) Exited() bool](#ProcessState.Exited)
-   [func (p \*ProcessState) Pid() int](#ProcessState.Pid)
-   [func (p \*ProcessState) String() string](#ProcessState.String)
-   [func (p \*ProcessState) Success() bool](#ProcessState.Success)
-   [func (p \*ProcessState) Sys() any](#ProcessState.Sys)
-   [func (p \*ProcessState) SysUsage() any](#ProcessState.SysUsage)
-   [func (p \*ProcessState) SystemTime()
    time.Duration](#ProcessState.SystemTime)
-   [func (p \*ProcessState) UserTime()
    time.Duration](#ProcessState.UserTime)
-   [type Signal](#Signal)
-   [type SyscallError](#SyscallError)
-   [func (e \*SyscallError) Error() string](#SyscallError.Error)
-   [func (e \*SyscallError) Timeout() bool](#SyscallError.Timeout)
-   [func (e \*SyscallError) Unwrap() error](#SyscallError.Unwrap)

 
### Examples

[Chmod](#example_Chmod)

[Chtimes](#example_Chtimes)

[CreateTemp](#example_CreateTemp)

[CreateTemp (Suffix)](#example_CreateTemp_suffix)

[ErrNotExist](#example_ErrNotExist)

[Expand](#example_Expand)

[ExpandEnv](#example_ExpandEnv)

[FileMode](#example_FileMode)

[Getenv](#example_Getenv)

[LookupEnv](#example_LookupEnv)

[Mkdir](#example_Mkdir)

[MkdirAll](#example_MkdirAll)

[MkdirTemp](#example_MkdirTemp)

[MkdirTemp (Suffix)](#example_MkdirTemp_suffix)

[OpenFile](#example_OpenFile)

[OpenFile (Append)](#example_OpenFile_append)

[ReadDir](#example_ReadDir)

[ReadFile](#example_ReadFile)

[Unsetenv](#example_Unsetenv)

[WriteFile](#example_WriteFile)


### Package files

dir.go dir\_unix.go dirent\_linux.go endian\_little.go env.go error.go
error\_errno.go error\_posix.go exec.go exec\_posix.go exec\_unix.go
executable.go executable\_procfs.go file.go file\_open\_unix.go
file\_posix.go file\_unix.go getwd.go path.go path\_unix.go
pipe2\_unix.go proc.go rawconn.go readfrom\_linux.go removeall\_at.go
stat.go stat\_linux.go stat\_unix.go sticky\_notbsd.go str.go sys.go
sys\_linux.go sys\_unix.go tempfile.go types.go types\_unix.go
wait\_waitid.go

Constants 
---------

Flags to OpenFile wrapping those of the underlying system. Not all flags
may be implemented on a given system.

```go
const (
    // Exactly one of O_RDONLY, O_WRONLY, or O_RDWR must be specified.
    O_RDONLY int = syscall.O_RDONLY // open the file read-only.
    O_WRONLY int = syscall.O_WRONLY // open the file write-only.
    O_RDWR   int = syscall.O_RDWR   // open the file read-write.
    // The remaining values may be or'ed in to control behavior.
    O_APPEND int = syscall.O_APPEND // append data to the file when writing.
    O_CREATE int = syscall.O_CREAT  // create a new file if none exists.
    O_EXCL   int = syscall.O_EXCL   // used with O_CREATE, file must not exist.
    O_SYNC   int = syscall.O_SYNC   // open for synchronous I/O.
    O_TRUNC  int = syscall.O_TRUNC  // truncate regular writable file when opened.
)
```

Seek whence values.

Deprecated: Use io.SeekStart, io.SeekCurrent, and io.SeekEnd.

```go
const (
    SEEK_SET int = 0 // seek relative to the origin of the file
    SEEK_CUR int = 1 // seek relative to the current offset
    SEEK_END int = 2 // seek relative to the end
)
```

```go
const (
    PathSeparator     = '/' // OS-specific path separator
    PathListSeparator = ':' // OS-specific path list separator
)
```

The defined file mode bits are the most significant bits of the
FileMode. The nine least-significant bits are the standard Unix
rwxrwxrwx permissions. The values of these bits should be considered
part of the public API and may be used in wire protocols or disk
representations: they must not be changed, although new bits might be
added.

```go
const (
    // The single letters are the abbreviations
    // used by the String method's formatting.
    ModeDir        = fs.ModeDir        // d: is a directory
    ModeAppend     = fs.ModeAppend     // a: append-only
    ModeExclusive  = fs.ModeExclusive  // l: exclusive use
    ModeTemporary  = fs.ModeTemporary  // T: temporary file; Plan 9 only
    ModeSymlink    = fs.ModeSymlink    // L: symbolic link
    ModeDevice     = fs.ModeDevice     // D: device file
    ModeNamedPipe  = fs.ModeNamedPipe  // p: named pipe (FIFO)
    ModeSocket     = fs.ModeSocket     // S: Unix domain socket
    ModeSetuid     = fs.ModeSetuid     // u: setuid
    ModeSetgid     = fs.ModeSetgid     // g: setgid
    ModeCharDevice = fs.ModeCharDevice // c: Unix character device, when ModeDevice is set
    ModeSticky     = fs.ModeSticky     // t: sticky
    ModeIrregular  = fs.ModeIrregular  // ?: non-regular file; nothing else is known about this file

    // Mask for the type bits. For regular files, none will be set.
    ModeType = fs.ModeType

    ModePerm = fs.ModePerm // Unix permission bits, 0o777
)
```

DevNull is the name of the operating system\'s "null device." On
Unix-like systems, it is \"/dev/null\"; on Windows, \"NUL\".

```go
const DevNull = "/dev/null"
```

Variables 
---------

Portable analogs of some common system call errors.

Errors returned from this package may be tested against these errors
with errors.Is.

```go
var (
    // ErrInvalid indicates an invalid argument.
    // Methods on File will return this error when the receiver is nil.
    ErrInvalid = fs.ErrInvalid // "invalid argument"

    ErrPermission = fs.ErrPermission // "permission denied"
    ErrExist      = fs.ErrExist      // "file already exists"
    ErrNotExist   = fs.ErrNotExist   // "file does not exist"
    ErrClosed     = fs.ErrClosed     // "file already closed"

    ErrNoDeadline       = errNoDeadline()       // "file type does not support deadline"
    ErrDeadlineExceeded = errDeadlineExceeded() // "i/o timeout"
)
```

Stdin, Stdout, and Stderr are open Files pointing to the standard input,
standard output, and standard error file descriptors.

Note that the Go runtime writes to standard error for panics and
crashes; closing Stderr may cause those messages to go elsewhere,
perhaps to a file opened later.

```go
var (
    Stdin  = NewFile(uintptr(syscall.Stdin), "/dev/stdin")
    Stdout = NewFile(uintptr(syscall.Stdout), "/dev/stdout")
    Stderr = NewFile(uintptr(syscall.Stderr), "/dev/stderr")
)
```

Args hold the command-line arguments, starting with the program name.

```go
var Args []string
```

ErrProcessDone indicates a Process has finished.

```go
var ErrProcessDone = errors.New("os: process already finished")
```

func Chdir 
----------

```go
func Chdir(dir string) error
```

Chdir changes the current working directory to the named directory. If
there is an error, it will be of type \*PathError.

func Chmod 
----------

```go
func Chmod(name string, mode FileMode) error
```

Chmod changes the mode of the named file to mode. If the file is a
symbolic link, it changes the mode of the link\'s target. If there is an
error, it will be of type \*PathError.

A different subset of the mode bits are used, depending on the operating
system.

On Unix, the mode\'s permission bits, ModeSetuid, ModeSetgid, and
ModeSticky are used.

On Windows, only the 0200 bit (owner writable) of mode is used; it
controls whether the file\'s read-only attribute is set or cleared. The
other bits are currently unused. For compatibility with Go 1.12 and
earlier, use a non-zero mode. Use mode 0400 for a read-only file and
0600 for a readable+writable file.

On Plan 9, the mode\'s permission bits, ModeAppend, ModeExclusive, and
ModeTemporary are used.

#### [Example]

Code:

```go
if err := os.Chmod("some-filename", 0644); err != nil {
    log.Fatal(err)
}
```

func Chown 
----------

```go
func Chown(name string, uid, gid int) error
```

Chown changes the numeric uid and gid of the named file. If the file is
a symbolic link, it changes the uid and gid of the link\'s target. A uid
or gid of -1 means to not change that value. If there is an error, it
will be of type \*PathError.

On Windows or Plan 9, Chown always returns the syscall.EWINDOWS or
EPLAN9 error, wrapped in \*PathError.

func Chtimes 
------------

```go
func Chtimes(name string, atime time.Time, mtime time.Time) error
```

Chtimes changes the access and modification times of the named file,
similar to the Unix utime() or utimes() functions. A zero time.Time
value will leave the corresponding file time unchanged.

The underlying filesystem may truncate or round the values to a less
precise time unit. If there is an error, it will be of type \*PathError.

#### [Example]

Code:

```go
mtime := time.Date(2006, time.February, 1, 3, 4, 5, 0, time.UTC)
atime := time.Date(2007, time.March, 2, 4, 5, 6, 0, time.UTC)
if err := os.Chtimes("some-filename", atime, mtime); err != nil {
    log.Fatal(err)
}
```

func Clearenv 
-------------

```go
func Clearenv()
```

Clearenv deletes all environment variables.

func DirFS 
-------------------------------------------

```go
func DirFS(dir string) fs.FS
```

DirFS returns a file system (an fs.FS) for the tree of files rooted at
the directory dir.

Note that DirFS(\"/prefix\") only guarantees that the Open calls it
makes to the operating system will begin with \"/prefix\":
DirFS(\"/prefix\").Open(\"file\") is the same as
os.Open(\"/prefix/file\"). So if /prefix/file is a symbolic link
pointing outside the /prefix tree, then using DirFS does not stop the
access any more than using os.Open does. Additionally, the root of the
fs.FS returned for a relative path, DirFS(\"prefix\"), will be affected
by later calls to Chdir. DirFS is therefore not a general substitute for
a chroot-style security mechanism when the directory tree contains
arbitrary content.

The directory dir must not be \"\".

The result implements io/fs.StatFS, io/fs.ReadFileFS and
io/fs.ReadDirFS.

func Environ 
------------

```go
func Environ() []string
```

Environ returns a copy of strings representing the environment, in the
form \"key=value\".

func Executable 
----------------------------------------------

```go
func Executable() (string, error)
```

Executable returns the path name for the executable that started the
current process. There is no guarantee that the path is still pointing
to the correct executable. If a symlink was used to start the process,
depending on the operating system, the result might be the symlink or
the path it pointed to. If a stable result is needed,
path/filepath.EvalSymlinks might help.

Executable returns an absolute path unless an error occurred.

The main use case is finding resources located relative to an
executable.

func Exit 
---------

```go
func Exit(code int)
```

Exit causes the current program to exit with the given status code.
Conventionally, code zero indicates success, non-zero an error. The
program terminates immediately; deferred functions are not run.

For portability, the status code should be in the range \[0, 125\].

func Expand 
-----------

```go
func Expand(s string, mapping func(string) string) string
```

Expand replaces \$\{var\} or \$var in the string based on the mapping
function. For example, os.ExpandEnv(s) is equivalent to os.Expand(s,
os.Getenv).

#### [Example]

Code:

```go
mapper := func(placeholderName string) string {
    switch placeholderName {
    case "DAY_PART":
        return "morning"
    case "NAME":
        return "Gopher"
    }

    return ""
}

fmt.Println(os.Expand("Good ${DAY_PART}, $NAME!", mapper))
```

Output:

```go
Good morning, Gopher!
```

func ExpandEnv 
--------------

```go
func ExpandEnv(s string) string
```

ExpandEnv replaces \$\{var\} or \$var in the string according to the
values of the current environment variables. References to undefined
variables are replaced by the empty string.

#### [Example]

Code:

```go
os.Setenv("NAME", "gopher")
os.Setenv("BURROW", "/usr/gopher")

fmt.Println(os.ExpandEnv("$NAME lives in ${BURROW}."))
```

Output:

```go
gopher lives in /usr/gopher.
```

func Getegid 
------------

```go
func Getegid() int
```

Getegid returns the numeric effective group id of the caller.

On Windows, it returns -1.

func Getenv 
-----------

```go
func Getenv(key string) string
```

Getenv retrieves the value of the environment variable named by the key.
It returns the value, which will be empty if the variable is not
present. To distinguish between an empty value and an unset value, use
LookupEnv.

#### [Example]

Code:

```go
os.Setenv("NAME", "gopher")
os.Setenv("BURROW", "/usr/gopher")

fmt.Printf("%s lives in %s.\n", os.Getenv("NAME"), os.Getenv("BURROW"))
```

Output:

```go
gopher lives in /usr/gopher.
```

func Geteuid 
------------

```go
func Geteuid() int
```

Geteuid returns the numeric effective user id of the caller.

On Windows, it returns -1.

func Getgid 
-----------

```go
func Getgid() int
```

Getgid returns the numeric group id of the caller.

On Windows, it returns -1.

func Getgroups 
--------------

```go
func Getgroups() ([]int, error)
```

Getgroups returns a list of the numeric ids of groups that the caller
belongs to.

On Windows, it returns syscall.EWINDOWS. See the os/user package for a
possible alternative.

func Getpagesize 
----------------

```go
func Getpagesize() int
```

Getpagesize returns the underlying system\'s memory page size.

func Getpid 
-----------

```go
func Getpid() int
```

Getpid returns the process id of the caller.

func Getppid 
------------

```go
func Getppid() int
```

Getppid returns the process id of the caller\'s parent.

func Getuid 
-----------

```go
func Getuid() int
```

Getuid returns the numeric user id of the caller.

On Windows, it returns -1.

func Getwd 
----------

```go
func Getwd() (dir string, err error)
```

Getwd returns a rooted path name corresponding to the current directory.
If the current directory can be reached via multiple paths (due to
symbolic links), Getwd may return any one of them.

func Hostname 
-------------

```go
func Hostname() (name string, err error)
```

Hostname returns the host name reported by the kernel.

func IsExist 
------------

```go
func IsExist(err error) bool
```

IsExist returns a boolean indicating whether the error is known to
report that a file or directory already exists. It is satisfied by
ErrExist as well as some syscall errors.

This function predates errors.Is. It only supports errors returned by
the os package. New code should use errors.Is(err, fs.ErrExist).

func IsNotExist 
---------------

```go
func IsNotExist(err error) bool
```

IsNotExist returns a boolean indicating whether the error is known to
report that a file or directory does not exist. It is satisfied by
ErrNotExist as well as some syscall errors.

This function predates errors.Is. It only supports errors returned by
the os package. New code should use errors.Is(err, fs.ErrNotExist).

func IsPathSeparator 
--------------------

```go
func IsPathSeparator(c uint8) bool
```

IsPathSeparator reports whether c is a directory separator character.

func IsPermission 
-----------------

```go
func IsPermission(err error) bool
```

IsPermission returns a boolean indicating whether the error is known to
report that permission is denied. It is satisfied by ErrPermission as
well as some syscall errors.

This function predates errors.Is. It only supports errors returned by
the os package. New code should use errors.Is(err, fs.ErrPermission).

func IsTimeout 
-----------------------------------------------

```go
func IsTimeout(err error) bool
```

IsTimeout returns a boolean indicating whether the error is known to
report that a timeout occurred.

This function predates errors.Is, and the notion of whether an error
indicates a timeout can be ambiguous. For example, the Unix error
EWOULDBLOCK sometimes indicates a timeout and sometimes does not. New
code should use errors.Is with a value appropriate to the call returning
the error, such as os.ErrDeadlineExceeded.

func Lchown 
-----------

```go
func Lchown(name string, uid, gid int) error
```

Lchown changes the numeric uid and gid of the named file. If the file is
a symbolic link, it changes the uid and gid of the link itself. If there
is an error, it will be of type \*PathError.

On Windows, it always returns the syscall.EWINDOWS error, wrapped in
\*PathError.

func Link 
---------

```go
func Link(oldname, newname string) error
```

Link creates newname as a hard link to the oldname file. If there is an
error, it will be of type \*LinkError.

func LookupEnv 
---------------------------------------------

```go
func LookupEnv(key string) (string, bool)
```

LookupEnv retrieves the value of the environment variable named by the
key. If the variable is present in the environment the value (which may
be empty) is returned and the boolean is true. Otherwise the returned
value will be empty and the boolean will be false.

#### [Example]

Code:

```go
show := func(key string) {
    val, ok := os.LookupEnv(key)
    if !ok {
        fmt.Printf("%s not set\n", key)
    } else {
        fmt.Printf("%s=%s\n", key, val)
    }
}

os.Setenv("SOME_KEY", "value")
os.Setenv("EMPTY_KEY", "")

show("SOME_KEY")
show("EMPTY_KEY")
show("MISSING_KEY")
```

Output:

```go
SOME_KEY=value
EMPTY_KEY=
MISSING_KEY not set
```

func Mkdir 
----------

```go
func Mkdir(name string, perm FileMode) error
```

Mkdir creates a new directory with the specified name and permission
bits (before umask). If there is an error, it will be of type
\*PathError.

#### [Example]

Code:

```go
err := os.Mkdir("testdir", 0750)
if err != nil && !os.IsExist(err) {
    log.Fatal(err)
}
err = os.WriteFile("testdir/testfile.txt", []byte("Hello, Gophers!"), 0660)
if err != nil {
    log.Fatal(err)
}
```

func MkdirAll 
-------------

```go
func MkdirAll(path string, perm FileMode) error
```

MkdirAll creates a directory named path, along with any necessary
parents, and returns nil, or else returns an error. The permission bits
perm (before umask) are used for all directories that MkdirAll creates.
If path is already a directory, MkdirAll does nothing and returns nil.

#### [Example]

Code:

```go
err := os.MkdirAll("test/subdir", 0750)
if err != nil {
    log.Fatal(err)
}
err = os.WriteFile("test/subdir/testfile.txt", []byte("Hello, Gophers!"), 0660)
if err != nil {
    log.Fatal(err)
}
```

func MkdirTemp 
-----------------------------------------------

```go
func MkdirTemp(dir, pattern string) (string, error)
```

MkdirTemp creates a new temporary directory in the directory dir and
returns the pathname of the new directory. The new directory\'s name is
generated by adding a random string to the end of pattern. If pattern
includes a \"\*\", the random string replaces the last \"\*\" instead.
If dir is the empty string, MkdirTemp uses the default directory for
temporary files, as returned by TempDir. Multiple programs or goroutines
calling MkdirTemp simultaneously will not choose the same directory. It
is the caller\'s responsibility to remove the directory when it is no
longer needed.

#### [Example]

Code:

```go
dir, err := os.MkdirTemp("", "example")
if err != nil {
    log.Fatal(err)
}
defer os.RemoveAll(dir) // clean up

file := filepath.Join(dir, "tmpfile")
if err := os.WriteFile(file, []byte("content"), 0666); err != nil {
    log.Fatal(err)
}
```

#### [Example (Suffix)]

Code:

```go
logsDir, err := os.MkdirTemp("", "*-logs")
if err != nil {
    log.Fatal(err)
}
defer os.RemoveAll(logsDir) // clean up

// Logs can be cleaned out earlier if needed by searching
// for all directories whose suffix ends in *-logs.
globPattern := filepath.Join(os.TempDir(), "*-logs")
matches, err := filepath.Glob(globPattern)
if err != nil {
    log.Fatalf("Failed to match %q: %v", globPattern, err)
}

for _, match := range matches {
    if err := os.RemoveAll(match); err != nil {
        log.Printf("Failed to remove %q: %v", match, err)
    }
}
```

func NewSyscallError 
--------------------

```go
func NewSyscallError(syscall string, err error) error
```

NewSyscallError returns, as an error, a new SyscallError with the given
system call name and error details. As a convenience, if err is nil,
NewSyscallError returns nil.

func Pipe 
---------

```go
func Pipe() (r *File, w *File, err error)
```

Pipe returns a connected pair of Files; reads from r return bytes
written to w. It returns the files and an error, if any.

func ReadFile 1.16
----------------------------------------------

```go
func ReadFile(name string) ([]byte, error)
```

ReadFile reads the named file and returns the contents. A successful
call returns err == nil, not err == EOF. Because ReadFile reads the
whole file, it does not treat an EOF from Read as an error to be
reported.

#### [Example]

Code:

```go
data, err := os.ReadFile("testdata/hello")
if err != nil {
    log.Fatal(err)
}
os.Stdout.Write(data)
```

Output:

```go
Hello, Gophers!
```

func Readlink 
-------------

```go
func Readlink(name string) (string, error)
```

Readlink returns the destination of the named symbolic link. If there is
an error, it will be of type \*PathError.

func Remove 
-----------

```go
func Remove(name string) error
```

Remove removes the named file or (empty) directory. If there is an
error, it will be of type \*PathError.

func RemoveAll 
--------------

```go
func RemoveAll(path string) error
```

RemoveAll removes path and any children it contains. It removes
everything it can but returns the first error it encounters. If the path
does not exist, RemoveAll returns nil (no error). If there is an error,
it will be of type \*PathError.

func Rename 
-----------

```go
func Rename(oldpath, newpath string) error
```

Rename renames (moves) oldpath to newpath. If newpath already exists and
is not a directory, Rename replaces it. OS-specific restrictions may
apply when oldpath and newpath are in different directories. Even within
the same directory, on non-Unix platforms Rename is not an atomic
operation. If there is an error, it will be of type \*LinkError.

func SameFile 
-------------

```go
func SameFile(fi1, fi2 FileInfo) bool
```

SameFile reports whether fi1 and fi2 describe the same file. For
example, on Unix this means that the device and inode fields of the two
underlying structures are identical; on other systems the decision may
be based on the path names. SameFile only applies to results returned by
this package\'s Stat. It returns false in other cases.

func Setenv 
-----------

```go
func Setenv(key, value string) error
```

Setenv sets the value of the environment variable named by the key. It
returns an error, if any.

func Symlink 
------------

```go
func Symlink(oldname, newname string) error
```

Symlink creates newname as a symbolic link to oldname. On Windows, a
symlink to a non-existent oldname creates a file symlink; if oldname is
later created as a directory the symlink will not work. If there is an
error, it will be of type \*LinkError.

func TempDir 
------------

```go
func TempDir() string
```

TempDir returns the default directory to use for temporary files.

On Unix systems, it returns \$TMPDIR if non-empty, else /tmp. On
Windows, it uses GetTempPath, returning the first non-empty value from
%TMP%, %TEMP%, %USERPROFILE%, or the Windows directory. On Plan 9, it
returns /tmp.

The directory is neither guaranteed to exist nor have accessible
permissions.

func Truncate 
-------------

```go
func Truncate(name string, size int64) error
```

Truncate changes the size of the named file. If the file is a symbolic
link, it changes the size of the link\'s target. If there is an error,
it will be of type \*PathError.

func Unsetenv 
--------------------------------------------

```go
func Unsetenv(key string) error
```

Unsetenv unsets a single environment variable.

#### [Example]

Code:

```go
os.Setenv("TMPDIR", "/my/tmp")
defer os.Unsetenv("TMPDIR")
```

func UserCacheDir 
--------------------------------------------------

```go
func UserCacheDir() (string, error)
```

UserCacheDir returns the default root directory to use for user-specific
cached data. Users should create their own application-specific
subdirectory within this one and use that.

On Unix systems, it returns \$XDG\_CACHE\_HOME as specified by
https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html>
if non-empty, else \$HOME/.cache. On Darwin, it returns
\$HOME/Library/Caches. On Windows, it returns %LocalAppData%. On Plan 9,
it returns \$home/lib/cache.

If the location cannot be determined (for example, \$HOME is not
defined), then it will return an error.

func UserConfigDir 
---------------------------------------------------

```go
func UserConfigDir() (string, error)
```

UserConfigDir returns the default root directory to use for
user-specific configuration data. Users should create their own
application-specific subdirectory within this one and use that.

On Unix systems, it returns \$XDG\_CONFIG\_HOME as specified by
https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html>
if non-empty, else \$HOME/.config. On Darwin, it returns
\$HOME/Library/Application Support. On Windows, it returns %AppData%. On
Plan 9, it returns \$home/lib.

If the location cannot be determined (for example, \$HOME is not
defined), then it will return an error.

func UserHomeDir 
-------------------------------------------------

```go
func UserHomeDir() (string, error)
```

UserHomeDir returns the current user\'s home directory.

On Unix, including macOS, it returns the \$HOME environment variable. On
Windows, it returns %USERPROFILE%. On Plan 9, it returns the \$home
environment variable.

If the expected variable is not set in the environment, UserHomeDir
returns either a platform-specific default value or a non-nil error.

func WriteFile 
-----------------------------------------------

```go
func WriteFile(name string, data []byte, perm FileMode) error
```

WriteFile writes data to the named file, creating it if necessary. If
the file does not exist, WriteFile creates it with permissions perm
(before umask); otherwise WriteFile truncates it before writing, without
changing permissions. Since WriteFile requires multiple system calls to
complete, a failure mid-operation can leave the file in a partially
written state.

#### [Example]

Code:

```go
err := os.WriteFile("testdata/hello", []byte("Hello, Gophers!"), 0666)
if err != nil {
    log.Fatal(err)
}
```

type DirEntry 
----------------------------------------------

A DirEntry is an entry read from a directory (using the ReadDir function
or a File\'s ReadDir method).

```go
type DirEntry = fs.DirEntry
```

### func ReadDir 

```go
func ReadDir(name string) ([]DirEntry, error)
```

ReadDir reads the named directory, returning all its directory entries
sorted by filename. If an error occurs reading the directory, ReadDir
returns the entries it was able to read before the error, along with the
error.

#### [Example]

Code:

```go
files, err := os.ReadDir(".")
if err != nil {
    log.Fatal(err)
}

for _, file := range files {
    fmt.Println(file.Name())
}
```

type File 
---------

File represents an open file descriptor.

```go
type File struct {
    // contains filtered or unexported fields
}
```

### func Create 

```go
func Create(name string) (*File, error)
```

Create creates or truncates the named file. If the file already exists,
it is truncated. If the file does not exist, it is created with mode
0666 (before umask). If successful, methods on the returned File can be
used for I/O; the associated file descriptor has mode O\_RDWR. If there
is an error, it will be of type \*PathError.

### func CreateTemp 

```go
func CreateTemp(dir, pattern string) (*File, error)
```

CreateTemp creates a new temporary file in the directory dir, opens the
file for reading and writing, and returns the resulting file. The
filename is generated by taking pattern and adding a random string to
the end. If pattern includes a \"\*\", the random string replaces the
last \"\*\". If dir is the empty string, CreateTemp uses the default
directory for temporary files, as returned by TempDir. Multiple programs
or goroutines calling CreateTemp simultaneously will not choose the same
file. The caller can use the file\'s Name method to find the pathname of
the file. It is the caller\'s responsibility to remove the file when it
is no longer needed.

#### [Example]

Code:

```go
f, err := os.CreateTemp("", "example")
if err != nil {
    log.Fatal(err)
}
defer os.Remove(f.Name()) // clean up

if _, err := f.Write([]byte("content")); err != nil {
    log.Fatal(err)
}
if err := f.Close(); err != nil {
    log.Fatal(err)
}
```

#### [Example (Suffix)]

Code:

```go
f, err := os.CreateTemp("", "example.*.txt")
if err != nil {
    log.Fatal(err)
}
defer os.Remove(f.Name()) // clean up

if _, err := f.Write([]byte("content")); err != nil {
    f.Close()
    log.Fatal(err)
}
if err := f.Close(); err != nil {
    log.Fatal(err)
}
```

### func NewFile 

```go
func NewFile(fd uintptr, name string) *File
```

NewFile returns a new File with the given file descriptor and name. The
returned value will be nil if fd is not a valid file descriptor. On Unix
systems, if the file descriptor is in non-blocking mode, NewFile will
attempt to return a pollable File (one for which the SetDeadline methods
work).

After passing it to NewFile, fd may become invalid under the same
conditions described in the comments of the Fd method, and the same
constraints apply.

### func Open 

```go
func Open(name string) (*File, error)
```

Open opens the named file for reading. If successful, methods on the
returned file can be used for reading; the associated file descriptor
has mode O\_RDONLY. If there is an error, it will be of type
\*PathError.

### func OpenFile 

```go
func OpenFile(name string, flag int, perm FileMode) (*File, error)
```

OpenFile is the generalized open call; most users will use Open or
Create instead. It opens the named file with specified flag (O\_RDONLY
etc.). If the file does not exist, and the O\_CREATE flag is passed, it
is created with mode perm (before umask). If successful, methods on the
returned File can be used for I/O. If there is an error, it will be of
type \*PathError.

#### [Example]

Code:

```go
f, err := os.OpenFile("notes.txt", os.O_RDWR|os.O_CREATE, 0755)
if err != nil {
    log.Fatal(err)
}
if err := f.Close(); err != nil {
    log.Fatal(err)
}
```

#### [Example (Append)]

Code:

```go
// If the file doesn't exist, create it, or append to the file
f, err := os.OpenFile("access.log", os.O_APPEND|os.O_CREATE|os.O_WRONLY, 0644)
if err != nil {
    log.Fatal(err)
}
if _, err := f.Write([]byte("appended some data\n")); err != nil {
    f.Close() // ignore error; Write error takes precedence
    log.Fatal(err)
}
if err := f.Close(); err != nil {
    log.Fatal(err)
}
```

### func (\*File) Chdir 

```go
func (f *File) Chdir() error
```

Chdir changes the current working directory to the file, which must be a
directory. If there is an error, it will be of type \*PathError.

### func (\*File) Chmod 

```go
func (f *File) Chmod(mode FileMode) error
```

Chmod changes the mode of the file to mode. If there is an error, it
will be of type \*PathError.

### func (\*File) Chown 

```go
func (f *File) Chown(uid, gid int) error
```

Chown changes the numeric uid and gid of the named file. If there is an
error, it will be of type \*PathError.

On Windows, it always returns the syscall.EWINDOWS error, wrapped in
\*PathError.

### func (\*File) Close 

```go
func (f *File) Close() error
```

Close closes the File, rendering it unusable for I/O. On files that
support SetDeadline, any pending I/O operations will be canceled and
return immediately with an ErrClosed error. Close will return an error
if it has already been called.

### func (\*File) Fd 

```go
func (f *File) Fd() uintptr
```

Fd returns the integer Unix file descriptor referencing the open file.
If f is closed, the file descriptor becomes invalid. If f is garbage
collected, a finalizer may close the file descriptor, making it invalid;
see runtime.SetFinalizer for more information on when a finalizer might
be run. On Unix systems this will cause the SetDeadline methods to stop
working. Because file descriptors can be reused, the returned file
descriptor may only be closed through the Close method of f, or by its
finalizer during garbage collection. Otherwise, during garbage
collection the finalizer may close an unrelated file descriptor with the
same (reused) number.

As an alternative, see the f.SyscallConn method.

### func (\*File) Name 

```go
func (f *File) Name() string
```

Name returns the name of the file as presented to Open.

### func (\*File) Read 

```go
func (f *File) Read(b []byte) (n int, err error)
```

Read reads up to len(b) bytes from the File and stores them in b. It
returns the number of bytes read and any error encountered. At end of
file, Read returns 0, io.EOF.

### func (\*File) ReadAt 

```go
func (f *File) ReadAt(b []byte, off int64) (n int, err error)
```

ReadAt reads len(b) bytes from the File starting at byte offset off. It
returns the number of bytes read and the error, if any. ReadAt always
returns a non-nil error when n \< len(b). At end of file, that error is
io.EOF.

### func (\*File) ReadDir 

```go
func (f *File) ReadDir(n int) ([]DirEntry, error)
```

ReadDir reads the contents of the directory associated with the file f
and returns a slice of DirEntry values in directory order. Subsequent
calls on the same file will yield later DirEntry records in the
directory.

If n \> 0, ReadDir returns at most n DirEntry records. In this case, if
ReadDir returns an empty slice, it will return an error explaining why.
At the end of a directory, the error is io.EOF.

If n \<= 0, ReadDir returns all the DirEntry records remaining in the
directory. When it succeeds, it returns a nil error (not io.EOF).

### func (\*File) ReadFrom 

```go
func (f *File) ReadFrom(r io.Reader) (n int64, err error)
```

ReadFrom implements io.ReaderFrom.

### func (\*File) Readdir 

```go
func (f *File) Readdir(n int) ([]FileInfo, error)
```

Readdir reads the contents of the directory associated with file and
returns a slice of up to n FileInfo values, as would be returned by
Lstat, in directory order. Subsequent calls on the same file will yield
further FileInfos.

If n \> 0, Readdir returns at most n FileInfo structures. In this case,
if Readdir returns an empty slice, it will return a non-nil error
explaining why. At the end of a directory, the error is io.EOF.

If n \<= 0, Readdir returns all the FileInfo from the directory in a
single slice. In this case, if Readdir succeeds (reads all the way to
the end of the directory), it returns the slice and a nil error. If it
encounters an error before the end of the directory, Readdir returns the
FileInfo read until that point and a non-nil error.

Most clients are better served by the more efficient ReadDir method.

### func (\*File) Readdirnames 

```go
func (f *File) Readdirnames(n int) (names []string, err error)
```

Readdirnames reads the contents of the directory associated with file
and returns a slice of up to n names of files in the directory, in
directory order. Subsequent calls on the same file will yield further
names.

If n \> 0, Readdirnames returns at most n names. In this case, if
Readdirnames returns an empty slice, it will return a non-nil error
explaining why. At the end of a directory, the error is io.EOF.

If n \<= 0, Readdirnames returns all the names from the directory in a
single slice. In this case, if Readdirnames succeeds (reads all the way
to the end of the directory), it returns the slice and a nil error. If
it encounters an error before the end of the directory, Readdirnames
returns the names read until that point and a non-nil error.

### func (\*File) Seek 

```go
func (f *File) Seek(offset int64, whence int) (ret int64, err error)
```

Seek sets the offset for the next Read or Write on file to offset,
interpreted according to whence: 0 means relative to the origin of the
file, 1 means relative to the current offset, and 2 means relative to
the end. It returns the new offset and an error, if any. The behavior of
Seek on a file opened with O\_APPEND is not specified.

### func (\*File) SetDeadline 

```go
func (f *File) SetDeadline(t time.Time) error
```

SetDeadline sets the read and write deadlines for a File. It is
equivalent to calling both SetReadDeadline and SetWriteDeadline.

Only some kinds of files support setting a deadline. Calls to
SetDeadline for files that do not support deadlines will return
ErrNoDeadline. On most systems ordinary files do not support deadlines,
but pipes do.

A deadline is an absolute time after which I/O operations fail with an
error instead of blocking. The deadline applies to all future and
pending I/O, not just the immediately following call to Read or Write.
After a deadline has been exceeded, the connection can be refreshed by
setting a deadline in the future.

If the deadline is exceeded a call to Read or Write or to other I/O
methods will return an error that wraps ErrDeadlineExceeded. This can be
tested using errors.Is(err, os.ErrDeadlineExceeded). That error
implements the Timeout method, and calling the Timeout method will
return true, but there are other possible errors for which the Timeout
will return true even if the deadline has not been exceeded.

An idle timeout can be implemented by repeatedly extending the deadline
after successful Read or Write calls.

A zero value for t means I/O operations will not time out.

### func (\*File) SetReadDeadline 

```go
func (f *File) SetReadDeadline(t time.Time) error
```

SetReadDeadline sets the deadline for future Read calls and any
currently-blocked Read call. A zero value for t means Read will not time
out. Not all files support setting deadlines; see SetDeadline.

### func (\*File) SetWriteDeadline 

```go
func (f *File) SetWriteDeadline(t time.Time) error
```

SetWriteDeadline sets the deadline for any future Write calls and any
currently-blocked Write call. Even if Write times out, it may return n
\> 0, indicating that some of the data was successfully written. A zero
value for t means Write will not time out. Not all files support setting
deadlines; see SetDeadline.

### func (\*File) Stat 

```go
func (f *File) Stat() (FileInfo, error)
```

Stat returns the FileInfo structure describing file. If there is an
error, it will be of type \*PathError.

### func (\*File) Sync 

```go
func (f *File) Sync() error
```

Sync commits the current contents of the file to stable storage.
Typically, this means flushing the file system\'s in-memory copy of
recently written data to disk.

### func (\*File) SyscallConn 

```go
func (f *File) SyscallConn() (syscall.RawConn, error)
```

SyscallConn returns a raw file. This implements the syscall.Conn
interface.

### func (\*File) Truncate 

```go
func (f *File) Truncate(size int64) error
```

Truncate changes the size of the file. It does not change the I/O
offset. If there is an error, it will be of type \*PathError.

### func (\*File) Write 

```go
func (f *File) Write(b []byte) (n int, err error)
```

Write writes len(b) bytes from b to the File. It returns the number of
bytes written and an error, if any. Write returns a non-nil error when n
!= len(b).

### func (\*File) WriteAt 

```go
func (f *File) WriteAt(b []byte, off int64) (n int, err error)
```

WriteAt writes len(b) bytes to the File starting at byte offset off. It
returns the number of bytes written and an error, if any. WriteAt
returns a non-nil error when n != len(b).

If file was opened with the O\_APPEND flag, WriteAt returns an error.

### func (\*File) WriteString 

```go
func (f *File) WriteString(s string) (n int, err error)
```

WriteString is like Write, but writes the contents of string s rather
than a slice of bytes.

type FileInfo 
-------------

A FileInfo describes a file and is returned by Stat and Lstat.

```go
type FileInfo = fs.FileInfo
```

### func Lstat 

```go
func Lstat(name string) (FileInfo, error)
```

Lstat returns a FileInfo describing the named file. If the file is a
symbolic link, the returned FileInfo describes the symbolic link. Lstat
makes no attempt to follow the link. If there is an error, it will be of
type \*PathError.

### func Stat 

```go
func Stat(name string) (FileInfo, error)
```

Stat returns a FileInfo describing the named file. If there is an error,
it will be of type \*PathError.

type FileMode 
-------------

A FileMode represents a file\'s mode and permission bits. The bits have
the same definition on all systems, so that information about files can
be moved from one system to another portably. Not all bits apply to all
systems. The only required bit is ModeDir for directories.

```go
type FileMode = fs.FileMode
```

#### [Example]

Code:

```go
fi, err := os.Lstat("some-filename")
if err != nil {
    log.Fatal(err)
}

fmt.Printf("permissions: %#o\n", fi.Mode().Perm()) // 0400, 0777, etc.
switch mode := fi.Mode(); {
case mode.IsRegular():
    fmt.Println("regular file")
case mode.IsDir():
    fmt.Println("directory")
case mode&fs.ModeSymlink != 0:
    fmt.Println("symbolic link")
case mode&fs.ModeNamedPipe != 0:
    fmt.Println("named pipe")
}
```

type LinkError 
--------------

LinkError records an error during a link or symlink or rename system
call and the paths that caused it.

```go
type LinkError struct {
    Op  string
    Old string
    New string
    Err error
}
```

### func (\*LinkError) Error 

```go
func (e *LinkError) Error() string
```

### func (\*LinkError) Unwrap 

```go
func (e *LinkError) Unwrap() error
```

type PathError 
--------------

PathError records an error and the operation and file path that caused
it.

```go
type PathError = fs.PathError
```

type ProcAttr 
-------------

ProcAttr holds the attributes that will be applied to a new process
started by StartProcess.

```go
type ProcAttr struct {
    // If Dir is non-empty, the child changes into the directory before
    // creating the process.
    Dir string
    // If Env is non-nil, it gives the environment variables for the
    // new process in the form returned by Environ.
    // If it is nil, the result of Environ will be used.
    Env []string
    // Files specifies the open files inherited by the new process. The
    // first three entries correspond to standard input, standard output, and
    // standard error. An implementation may support additional entries,
    // depending on the underlying operating system. A nil entry corresponds
    // to that file being closed when the process starts.
    // On Unix systems, StartProcess will change these File values
    // to blocking mode, which means that SetDeadline will stop working
    // and calling Close will not interrupt a Read or Write.
    Files []*File

    // Operating system-specific process creation attributes.
    // Note that setting this field means that your program
    // may not execute properly or even compile on some
    // operating systems.
    Sys *syscall.SysProcAttr
}
```

type Process 
------------

Process stores the information about a process created by StartProcess.

```go
type Process struct {
    Pid int
    // contains filtered or unexported fields
}
```

### func FindProcess 

```go
func FindProcess(pid int) (*Process, error)
```

FindProcess looks for a running process by its pid.

The Process it returns can be used to obtain information about the
underlying operating system process.

On Unix systems, FindProcess always succeeds and returns a Process for
the given pid, regardless of whether the process exists. To test whether
the process actually exists, see whether p.Signal(syscall.Signal(0))
reports an error.

### func StartProcess 

```go
func StartProcess(name string, argv []string, attr *ProcAttr) (*Process, error)
```

StartProcess starts a new process with the program, arguments and
attributes specified by name, argv and attr. The argv slice will become
os.Args in the new process, so it normally starts with the program name.

If the calling goroutine has locked the operating system thread with
runtime.LockOSThread and modified any inheritable OS-level thread state
(for example, Linux or Plan 9 name spaces), the new process will inherit
the caller\'s thread state.

StartProcess is a low-level interface. The os/exec package provides
higher-level interfaces.

If there is an error, it will be of type \*PathError.

### func (\*Process) Kill 

```go
func (p *Process) Kill() error
```

Kill causes the Process to exit immediately. Kill does not wait until
the Process has actually exited. This only kills the Process itself, not
any other processes it may have started.

### func (\*Process) Release 

```go
func (p *Process) Release() error
```

Release releases any resources associated with the Process p, rendering
it unusable in the future. Release only needs to be called if Wait is
not.

### func (\*Process) Signal 

```go
func (p *Process) Signal(sig Signal) error
```

Signal sends a signal to the Process. Sending Interrupt on Windows is
not implemented.

### func (\*Process) Wait 

```go
func (p *Process) Wait() (*ProcessState, error)
```

Wait waits for the Process to exit, and then returns a ProcessState
describing its status and an error, if any. Wait releases any resources
associated with the Process. On most operating systems, the Process must
be a child of the current process or an error will be returned.

type ProcessState 
-----------------

ProcessState stores information about a process, as reported by Wait.

```go
type ProcessState struct {
    // contains filtered or unexported fields
}
```

### func (\*ProcessState) ExitCode 

```go
func (p *ProcessState) ExitCode() int
```

ExitCode returns the exit code of the exited process, or -1 if the
process hasn\'t exited or was terminated by a signal.

### func (\*ProcessState) Exited 

```go
func (p *ProcessState) Exited() bool
```

Exited reports whether the program has exited. On Unix systems this
reports true if the program exited due to calling exit, but false if the
program terminated due to a signal.

### func (\*ProcessState) Pid 

```go
func (p *ProcessState) Pid() int
```

Pid returns the process id of the exited process.

### func (\*ProcessState) String 

```go
func (p *ProcessState) String() string
```

### func (\*ProcessState) Success 

```go
func (p *ProcessState) Success() bool
```

Success reports whether the program exited successfully, such as with
exit status 0 on Unix.

### func (\*ProcessState) Sys 

```go
func (p *ProcessState) Sys() any
```

Sys returns system-dependent exit information about the process. Convert
it to the appropriate underlying type, such as syscall.WaitStatus on
Unix, to access its contents.

### func (\*ProcessState) SysUsage 

```go
func (p *ProcessState) SysUsage() any
```

SysUsage returns system-dependent resource usage information about the
exited process. Convert it to the appropriate underlying type, such as
\*syscall.Rusage on Unix, to access its contents. (On Unix,
\*syscall.Rusage matches struct rusage as defined in the getrusage(2)
manual page.)

### func (\*ProcessState) SystemTime 

```go
func (p *ProcessState) SystemTime() time.Duration
```

SystemTime returns the system CPU time of the exited process and its
children.

### func (\*ProcessState) UserTime 

```go
func (p *ProcessState) UserTime() time.Duration
```

UserTime returns the user CPU time of the exited process and its
children.

type Signal 
-----------

A Signal represents an operating system signal. The usual underlying
implementation is operating system-dependent: on Unix it is
syscall.Signal.

```go
type Signal interface {
    String() string
    Signal() // to distinguish from other Stringers
}
```

The only signal values guaranteed to be present in the os package on all
systems are os.Interrupt (send the process an interrupt) and os.Kill
(force the process to exit). On Windows, sending os.Interrupt to a
process with os.Process.Signal is not implemented; it will return an
error instead of sending a signal.

```go
var (
    Interrupt Signal = syscall.SIGINT
    Kill      Signal = syscall.SIGKILL
)
```

type SyscallError 
-----------------

SyscallError records an error from a specific system call.

```go
type SyscallError struct {
    Syscall string
    Err     error
}
```

### func (\*SyscallError) Error 

```go
func (e *SyscallError) Error() string
```

### func (\*SyscallError) Timeout 

```go
func (e *SyscallError) Timeout() bool
```

Timeout reports whether this error represents a timeout.

### func (\*SyscallError) Unwrap 

```go
func (e *SyscallError) Unwrap() error
```

Subdirectories 
--------------

 
Name


Synopsis

[..](../index)

[exec](exec/index)

Package exec runs external commands.

[signal](signal/index)

Package signal implements access to incoming signals.

[user](user/index)

Package user allows user account lookups by name or id.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/os/>

