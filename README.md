# Process List Library for Go

This repository is forked from 'keybase' and added process user name by pizchen.

go-ps is a library for Go that implements OS-specific APIs to list and
manipulate processes in a platform-safe way. The library can find and
list processes on Linux, Mac OS X, and Windows.

If you're new to Go, this library has a good amount of advanced Go educational
value as well. It uses some advanced features of Go: build tags, accessing
DLL methods for Windows, cgo for Darwin, etc.

How it works:

  * **Darwin** uses `sysctl` and `proc_listpids` (for the path) to retrieve the process table, via cgo.
  * **Unix** uses the procfs at `/proc` to inspect the process tree.
  * **Windows** uses the Windows API, and methods such as
    `CreateToolhelp32Snapshot` to get a point-in-time snapshot of
    the process table.

## Installation

Install using standard `go get`:

```
$ go get github.com/pizchen/go-ps
```
