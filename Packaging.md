

## A package is a namespace for a collection/group of reusable entities like types & functions

Reusable entities like functions/structs/types etc. are grouped together in a namespace called **package**.

## A package (is usually a dir) can span across multiple files

The package name declaration is the first line of code in a go file.
Usually the package declaration name should match the containing dir of the file:
Here is an example: https://github.com/prometheus/prometheus/blob/main/scrape/clientprotobuf.go#L14

```go
// file: /path/to/myproject/mycollections/utils.go

// package declaration, all entities in current file belong to this package
package mycollections // matches containing dir name

func ContainsString(s []string, e string) bool {
    for _, a := range s {
        if a == e {
            return true
        }
    }
    return false
}
```

Non-executable libraries should always have a non-main package name.

A package statement is the first line in any go file.
A package can have more than one files.

## Importing a package

```go
import (
    pkgName // import all exported entities from pkgName
)
```


## Package naming convention

Package names are usually all lowercase, single words. **No underscores or mixedCaps.**

E.g. `strconv` allowed, `str_conv` or `strConv` is not allowed

