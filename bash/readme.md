# Bash

## find

If  the  whole  expression  contains  no  actions  other than -prune or -print, -print is performed on all files for which the whole expression is true.

That means by default :

```sh
find . -name foo -prune -o -type f
```
gets interpreted as
```sh
find . \( -name foo -prune -o -type f \) -print
```
But
```sh
find . -name foo -prune -o -type f -print
```
gets interpreted as
```sh
find . \( -name foo -prune -o -type f -print \)
```
and will print all the files from the current directory that are not under foo directories

### print all files from current directory that are not under a node_modules
```sh
find . -name node_modules -prune -o -type f -print
```