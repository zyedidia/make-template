Makefile templates for simple C and C++ programs.

Usage:

```
make [OPTIONS]
```

Possible options include

* `DEBUG=1`: enable debugging information (`-ggdb3`), optimize for debugging (`-Og`), and enable sanitizers.
* `SANITIZE=1`: enable sanitizers (address, undefined, leak, thread).
    * For thread sanitization, needs `WANT_TSAN=1`, for leak sanitization needs `LSAN=1`.
* `PTHREAD=1`: link with pthread library.
* `PROFILE=1`: write profile information for use with the analysis program `gprof` (`-pg`).
* `PIE=0`: disable generation of position independent executables.

These options can also be set directly inside the Makefile.

Possible targets are

* `all`: builds all programs.
* `format`: formats source files with `clang-format` (according to the style defined in the `.clang-format` file).
* `clean`: removes build files and executables.
