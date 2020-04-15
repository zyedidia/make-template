Makefile templates for simple C and C++ programs.

Usage:

```
make [TARGET] [OPTIONS]
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

* `all` (default): builds all programs.
* `format`: formats source files with `clang-format` (according to the style defined in the `.clang-format` file).
* `clean`: removes build files and executables.

Recommendation: for faster builds, set your `MAKEFLAGS` environment variable to use the full number of logical cores on your machine:

Linux:

```
export MAKEFLAGS="-j$(grep -c ^processor /proc/cpuinfo)"
```

MacOS:

```
export MAKEFLAGS="-j$(sysctl -n hw.ncpu)"
```
