# APT Dependencies

### Usage

`./dependencies.sh [OPTIONS] [--] <package>`

Print a list of installed packages that depend on a given package.

### Options
* `-h`, `--help`
  
  display this help and exit

* `--`
  
  everything after this will be treated as a list of packages.

### Arguments

The `<package>` argument will be treated as a single package. Valid regexp can
be used as well but should be between quotes. When multiple packages are
provided without using `--` only the last package will be used.

When `--` is provided, multiple packages or regexps can be provided, when
seperated by spaces and quoted when needed. This will override any package
provided before the `--`.

When multiple packages are provided, packages that depend on ANY of the
provided packages will be returned.
Dependencies can occur multiple times when providing multiple packages.
